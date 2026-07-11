using UnityEngine;
using System.Collections.Generic;

public class CarController : MonoBehaviour
{
    public enum TransmissionMode { Automatic, Manual }
    public enum ControlType { Buttons, SteeringWheel, Tilt }

    [Header("Driving Settings")]
    public float motorForce = 1500f;
    public float brakeForce = 3000f;
    public float maxSteerAngle = 35f;
    
    [Header("Transmission & Controls")]
    public TransmissionMode transmission = TransmissionMode.Automatic;
    public ControlType controlType = ControlType.Buttons;
    public int currentGear = 1;
    public float[] gearRatios = { 3.5f, 2.5f, 1.8f, 1.4f, 1.0f, 0.8f };

    [Header("Wheel Colliders")]
    public WheelCollider frontLeft;
    public WheelCollider frontRight;
    public WheelCollider rearLeft;
    public WheelCollider rearRight;

    private float horizontalInput;
    private float verticalInput;
    private bool isBraking;

    public void SetInputs(float move, float steer, bool brake)
    {
        verticalInput = move;
        horizontalInput = steer;
        isBraking = brake;
    }

    private void FixedUpdate()
    {
        HandleMotor();
        HandleSteering();
        UpdateWheels();
    }

    private void HandleMotor()
    {
        float torque = verticalInput * motorForce;
        
        if (transmission == TransmissionMode.Manual)
        {
            torque *= gearRatios[currentGear - 1];
        }

        rearLeft.motorTorque = torque;
        rearRight.motorTorque = torque;

        float currentBrake = isBraking ? brakeForce : 0f;
        ApplyBraking(currentBrake);
    }

    private void ApplyBraking(float force)
    {
        frontLeft.brakeTorque = force;
        frontRight.brakeTorque = force;
        rearLeft.brakeTorque = force / 2;
        rearRight.brakeTorque = force / 2;
    }

    private void HandleSteering()
    {
        float steerAngle = horizontalInput * maxSteerAngle;
        frontLeft.steerAngle = steerAngle;
        frontRight.steerAngle = steerAngle;
    }

    private void UpdateWheels()
    {
        UpdateSingleWheel(frontLeft);
        UpdateSingleWheel(frontRight);
        UpdateSingleWheel(rearLeft);
        UpdateSingleWheel(rearRight);
    }

    private void UpdateSingleWheel(WheelCollider collider)
    {
        if (collider.transform.childCount == 0) return;
        Transform visualWheel = collider.transform.GetChild(0);
        
        Vector3 position;
        Quaternion rotation;
        collider.GetWorldPose(out position, out rotation);
        
        visualWheel.position = position;
        visualWheel.rotation = rotation;
    }

    // Manual Gear Shifts
    public void GearUp() { if (currentGear < gearRatios.Length) currentGear++; }
    public void GearDown() { if (currentGear > 1) currentGear--; }
}
using UnityEngine;

public class MobileInputBridge : MonoBehaviour
{
    public CarController targetCar;
    
    private float moveInput;
    private float steerInput;
    private bool brakeInput;

    void Update()
    {
        if (targetCar == null) return;

        // Keyboard support for testing inside Unity Editor
        #if UNITY_EDITOR
        moveInput = Input.GetAxis("Vertical");
        steerInput = Input.GetAxis("Horizontal");
        brakeInput = Input.GetKey(KeyCode.Space);
        #endif

        targetCar.SetInputs(moveInput, steerInput, brakeInput);
    }

    // UI Buttons functions (Call these from UI Event Triggers)
    public void PressRace() => moveInput = 1f;
    public void ReleaseRace() => moveInput = 0f;
    
    public void PressReverse() => moveInput = -1f;
    public void ReleaseReverse() => moveInput = 0f;

    public void SteerLeft() => steerInput = -1f;
    public void SteerRight() => steerInput = 1f;
    public void ReleaseSteer() => steerInput = 0f;

    public void PressBrake(bool state) => brakeInput = state;
}
using UnityEngine;

public class CameraManager : MonoBehaviour
{
    public Transform carTarget;
    public Transform cockpitAnchor; // Place an empty GameObject inside car dashboard
    
    [Header("Third Person Settings")]
    public float distance = 6.0f;
    public float height = 2.0f;
    public float rotationDamping = 3.0f;
    public float heightDamping = 2.0f;

    private int cameraMode = 0; // 0 = Third Person, 1 = Cockpit

    public void ToggleCamera()
    {
        cameraMode = (cameraMode + 1) % 2;
    }

    void LateUpdate()
    {
        if (!carTarget) return;

        if (cameraMode == 0)
        {
            // Third Person Follow Physics
            float wantedRotationAngle = carTarget.eulerAngles.y;
            float wantedHeight = carTarget.position.y + height;

            float currentRotationAngle = transform.eulerAngles.y;
            float currentHeight = transform.position.y;

            currentRotationAngle = Mathf.LerpAngle(currentRotationAngle, wantedRotationAngle, rotationDamping * Time.deltaTime);
            currentHeight = Mathf.Lerp(currentHeight, wantedHeight, heightDamping * Time.deltaTime);

            Quaternion currentRotation = Quaternion.Euler(0, currentRotationAngle, 0);

            transform.position = carTarget.position;
            transform.position -= currentRotation * Vector3.forward * distance;

            transform.position = new Vector3(transform.position.x, currentHeight, transform.position.z);
            transform.LookAt(carTarget.position + Vector3.up * 0.5f);
        }
        else if (cameraMode == 1 && cockpitAnchor != null)
        {
            // Snap straight to Dashboard view
            transform.position = cockpitAnchor.position;
            transform.rotation = cockpitAnchor.rotation;
        }
    }
}

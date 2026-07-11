<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Workshop Motor Reminding | Expert AC/DC Motor & Pump Repair</title>
    <!-- Tailwind CSS for Professional Styling -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body { font-family: 'Inter', sans-serif; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800">

    <!-- Top Navigation Bar -->
    <nav class="bg-blue-900 text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo -->
                <div class="flex items-center gap-2 font-bold text-xl tracking-wide">
                    <i class="fas fa-cogs text-orange-400 text-2xl"></i>
                    <span>WORKSHOP<span class="text-orange-400">MOTOR</span></span>
                </div>
                
                <!-- Desktop Menu -->
                <div class="hidden md:flex items-center space-x-8 font-medium">
                    <a href="#" class="hover:text-orange-400 transition-colors">Home</a>
                    <a href="#about" class="hover:text-orange-400 transition-colors">Who We Are</a>
                    <a href="#services" class="hover:text-orange-400 transition-colors">Our Expertise</a>
                    <a href="#contact" class="hover:text-orange-400 transition-colors">Contact</a>
                </div>

                <!-- Hamburger Menu Button (Three Lines) -->
                <div class="md:hidden">
                    <button id="menu-btn" class="text-white hover:text-orange-400 focus:outline-none p-2 rounded transition-colors" aria-label="Toggle Menu">
                        <i class="fas fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Dropdown Menu (Initially Hidden) -->
        <div id="mobile-menu" class="hidden md:hidden bg-blue-950 border-t border-blue-800 px-4 pt-2 pb-4 space-y-2 transition-all duration-300">
            <a href="#" class="block py-2 px-3 rounded hover:bg-blue-800 transition-colors">Home</a>
            <a href="#about" class="block py-2 px-3 rounded hover:bg-blue-800 transition-colors">Who We Are</a>
            <a href="#services" class="block py-2 px-3 rounded hover:bg-blue-800 transition-colors">Our Expertise</a>
            <a href="#contact" class="block py-2 px-3 rounded hover:bg-blue-800 transition-colors">Contact</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative bg-gradient-to-r flow-root bg-blue-950 text-white py-20 px-4 text-center">
        <div class="max-w-3xl mx-auto space-y-6">
            <span class="inline-block bg-orange-500/20 text-orange-400 border border-orange-500/30 font-semibold text-xs uppercase px-3 py-1 rounded-full tracking-wider">
                Heavy Duty Electrical Services
            </span>
            <h1 class="text-4xl md:text-5xl font-extrabold leading-tight">
                Professional Motor <br class="hidden sm:inline"> Rewinding & Repair
            </h1>
            <p class="text-lg text-slate-300 max-w-xl mx-auto">
                Keep your machinery running flawlessly. We specialize in high-quality AC/DC motor rewinding, submersible pumps, and industrial electrical maintenance.
            </p>
            
            <!-- Quick Contact Buttons -->
            <div class="flex flex-col sm:flex-row justify-center gap-4 pt-4">
                <a href="tel:+919876543210" class="flex items-center justify-center gap-2 bg-blue-600 hover:bg-blue-700 text-white font-semibold px-6 py-3 rounded-lg shadow-md transition-all">
                    <i class="fas fa-phone-alt"></i> Call Now
                </a>
                <a href="https://wa.me/919876543210" target="_blank" class="flex items-center justify-center gap-2 bg-green-600 hover:bg-green-700 text-white font-semibold px-6 py-3 rounded-lg shadow-md transition-all">
                    <i class="fab fa-whatsapp text-xl"></i> WhatsApp Chat
                </a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-16 px-4 max-w-5xl mx-auto">
        <div class="grid md:grid-cols-3 gap-8 items-center">
            <div class="md:col-span-1 bg-gradient-to-br from-orange-400 to-orange-600 text-white p-8 rounded-2xl shadow-lg text-center md:text-left">
                <p class="text-sm font-bold uppercase tracking-wider opacity-90">Who We Are</p>
                <h2 class="text-3xl font-extrabold mt-2 leading-tight">Over 15 Years Of Excellence</h2>
            </div>
            <div class="md:col-span-2 space-y-4 text-slate-600 leading-relaxed text-base">
                <p>
                    At Workshop Motor Rewinding, we provide reliable, heavy-duty repair and winding services for all variants of electrical motors and pumps. Our state-of-the-art facility handles everything from micro-motors to massive industrial alternators.
                </p>
                <p>
                    We pride ourselves on using premium class insulation materials and pure copper winding to guarantee durability, optimal performance, and power efficiency for your machinery.
                </p>
            </div>
        </div>

        <!-- Trust Badges -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-12">
            <div class="flex items-start gap-4 bg-white p-5 rounded-xl shadow-sm border border-slate-100">
                <div class="bg-green-100 text-green-600 p-3 rounded-lg"><i class="fas fa-check-circle text-xl"></i></div>
                <div>
                    <h4 class="font-bold text-lg">Certified Techs</h4>
                    <p class="text-slate-500 text-sm mt-0.5">Highly experienced workforce for critical fixes.</p>
                </div>
            </div>
            <div class="flex items-start gap-4 bg-white p-5 rounded-xl shadow-sm border border-slate-100">
                <div class="bg-green-100 text-green-600 p-3 rounded-lg"><i class="fas fa-check-circle text-xl"></i></div>
                <div>
                    <h4 class="font-bold text-lg">Quick Turnaround</h4>
                    <p class="text-slate-500 text-sm mt-0.5">Minimizing your business and factory downtime.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Banner / Emergency Hotline -->
    <section id="contact" class="bg-blue-900 text-white py-12 px-4 text-center">
        <div class="max-w-2xl mx-auto space-y-4">
            <h3 class="text-2xl font-bold">Need Immediate Assistance?</h3>
            <p class="text-slate-300">If your factory motor or water pump went down unexpectedly, don't worry. Call our emergency hotline for quick drop-off or on-site analysis.</p>
            <div class="inline-flex items-center gap-3 bg-blue-950 px-6 py-3 rounded-xl border border-blue-800 font-mono text-xl text-orange-400 mt-2 font-bold shadow-inner">
                <i class="fas fa-phone-alt"></i> <span>+91 98765 43210</span>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-16 px-4 bg-slate-100">
        <div class="max-w-6xl mx-auto">
            <div class="text-center space-y-2 mb-12">
                <p class="text-orange-500 font-bold uppercase tracking-wider text-sm">Our Expertise</p>
                <h2 class="text-3xl font-extrabold text-slate-900">Comprehensive Workshop Services</h2>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Card 1 -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200 hover:shadow-md transition-shadow">
                    <div class="text-blue-600 text-3xl mb-4"><i class="fas fa-charging-station"></i></div>
                    <h3 class="font-bold text-lg mb-2">AC Motor Rewinding</h3>
                    <p class="text-slate-500 text-sm leading-relaxed">High-precision rewinding for single and three-phase induction AC motors.</p>
                </div>
                <!-- Card 2 -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200 hover:shadow-md transition-shadow">
                    <div class="text-blue-600 text-3xl mb-4"><i class="fas fa-battery-three-quarters"></i></div>
                    <h3 class="font-bold text-lg mb-2">DC Motor Rewinding</h3>
                    <p class="text-slate-500 text-sm leading-relaxed">Specialized armature and field coil rewinding for complex industrial DC machinery.</p>
                </div>
                <!-- Card 3 -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200 hover:shadow-md transition-shadow">
                    <div class="text-blue-600 text-3xl mb-4"><i class="fas fa-water"></i></div>
                    <h3 class="font-bold text-lg mb-2">Submersible Pump</h3>
                    <p class="text-slate-500 text-sm leading-relaxed">Complete overhaul, rewinding, and waterproof seal replacement for water pumps.</p>
                </div>
                <!-- Card 4 -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200 hover:shadow-md transition-shadow">
                    <div class="text-blue-600 text-3xl mb-4"><i class="fas fa-tools"></i></div>
                    <h3 class="font-bold text-lg mb-2">Industrial Maintenance</h3>
                    <p class="text-slate-500 text-sm leading-relaxed">Preventative care, bearing replacement, and dynamic insulation testing.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Core Advantages Section (Fixed the broken HTML here) -->
    <section class="py-16 px-4 max-w-5xl mx-auto">
        <div class="text-center space-y-2 mb-12">
            <p class="text-orange-500 font-bold uppercase tracking-wider text-sm">Our Advantages</p>
            <h2 class="text-3xl font-extrabold">Why Hundreds Trust Our Workshop</h2>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-3 gap-8 text-center">
            <div class="space-y-3 bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                <div class="text-orange-500 text-4xl"><i class="fas fa-gem"></i></div>
                <h3 class="font-bold text-lg">Pure Copper</h3>
                <p class="text-slate-500 text-sm">We strictly use 100% premium grade pure copper wire for long-lasting builds.</p>
            </div>
            <div class="space-y-3 bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                <div class="text-orange-500 text-4xl"><i class="fas fa-user-shield"></i></div>
                <h3 class="font-bold text-lg">Guaranteed Work</h3>
                <p class="text-slate-500 text-sm">All repairs go through rigid load and insulation stress tests before delivery.</p>
            </div>
            <div class="space-y-3 bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                <div class="text-orange-500 text-4xl"><i class="fas fa-hand-holding-usd"></i></div>
                <h3 class="font-bold text-lg">Fair Pricing</h3>
                <p class="text-slate-500 text-sm">Honest estimations with absolutely no hidden technical charges.</p>
            </div>
        </div>
    </section>

    <!-- JavaScript code to make the Hamburger Menu Work -->
    <script>
        const menuBtn = document.getElementById('menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');

        menuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Close menu when a link is clicked
        const navLinks = mobileMenu.querySelectorAll('a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });
    </script>
</body>
</html>

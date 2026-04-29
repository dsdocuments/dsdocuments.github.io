
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DSDocs | Professional Document Preparation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --ds-blue: #005696; /* Extracted from screenshots */
            --ds-dark: #003a66;
        }
        body { font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .serif { font-family: 'Playfair Display', serif; }
        .bg-ds-blue { background-color: var(--ds-blue); }
        .text-ds-blue { color: var(--ds-blue); }
        .border-ds-blue { border-color: var(--ds-blue); }
        
        .hero-overlay {
            background: linear-gradient(rgba(0, 58, 102, 0.8), rgba(0, 58, 102, 0.6));
        }
        
        .nav-link {
            position: relative;
            transition: color 0.3s;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -4px;
            left: 0;
            background-color: white;
            transition: width 0.3s;
        }
        .nav-link:hover::after { width: 100%; }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800">

    <!-- Navigation -->
    <nav class="bg-ds-blue text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center gap-2">
                    <span class="text-3xl font-bold tracking-tight">DS<span class="font-light">Docs</span></span>
                </div>
                <div class="hidden md:flex space-x-8 text-sm font-medium uppercase tracking-wider">
                    <a href="#home" class="nav-link">Home</a>
                    <a href="#services" class="nav-link">Our Services</a>
                    <a href="#about" class="nav-link">About Us</a>
                    <a href="#philosophy" class="nav-link">Our Philosophy</a>
                    <a href="#contact" class="nav-link">Contact Us</a>
                </div>
                <div class="md:hidden">
                    <button id="mobile-menu-btn" class="p-2">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
                    </button>
                </div>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-ds-dark px-4 py-6 space-y-4 border-t border-blue-400/20">
            <a href="#home" class="block">Home</a>
            <a href="#services" class="block">Our Services</a>
            <a href="#about" class="block">About Us</a>
            <a href="#philosophy" class="block">Our Philosophy</a>
            <a href="#contact" class="block">Contact Us</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative h-[600px] flex items-center justify-center text-center text-white">
        <div class="absolute inset-0 bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&q=80');"></div>
        <div class="absolute inset-0 hero-overlay"></div>
        <div class="relative z-10 px-4 max-w-4xl">
            <h2 class="text-xl md:text-2xl font-light tracking-[0.3em] uppercase mb-4">Your Document</h2>
            <h1 class="serif text-5xl md:text-7xl mb-8">Is Our Priority</h1>
            <div class="flex flex-col sm:flex-row justify-center gap-4 mt-8">
                <a href="#contact" class="px-8 py-3 border-2 border-white hover:bg-white hover:text-ds-blue transition-all font-bold uppercase tracking-widest text-sm">Contact Us</a>
                <div class="flex items-center justify-center gap-6 mt-4 sm:mt-0">
                    <a href="#" class="hover:text-blue-300 transition-colors"><svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                    <a href="#" class="hover:text-blue-300 transition-colors"><svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg></a>
                    <a href="#" class="hover:text-blue-300 transition-colors"><svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg></a>
                </div>
            </div>
        </div>
    </section>

    <!-- Quick Info -->
    <section class="py-16 bg-white border-b">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid md:grid-cols-3 gap-12">
                <div>
                    <h3 class="text-ds-blue font-bold text-lg mb-4">Round-the-clock service</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">Our company is deeply committed to your success. We prioritize your needs and work tirelessly to deliver exceptional service and solutions tailored to your specific goals. We are with you every step of the way.</p>
                </div>
                <div>
                    <h3 class="text-ds-blue font-bold text-lg mb-4">Services at affordable prices</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">Our company offers top-tier immigration drafting services at affordable prices, ensuring you receive expert support without breaking the bank. Whether you need assistance with document preparation, translation, or case management.</p>
                </div>
                <div>
                    <h3 class="text-ds-blue font-bold text-lg mb-4">Our business hours</h3>
                    <p class="text-slate-600 text-sm font-medium">Mon - Fri: 9:00 am - 5:00 pm</p>
                    <p class="text-slate-400 text-xs mt-2 italic">Weekend and After-hours support available via phone.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Core Highlights -->
    <section class="bg-ds-blue text-white py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row justify-around text-center gap-8">
                <div class="text-xl font-light tracking-widest">DISCREET</div>
                <div class="text-xl font-light tracking-widest">SPEED</div>
                <div class="text-xl font-light tracking-widest">DEPENDABILITY</div>
            </div>
        </div>
    </section>

    <!-- Our Services Section -->
    <section id="services" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="mb-16">
                <h2 class="serif text-4xl text-ds-blue mb-6">Our Service to You</h2>
                <p class="text-lg text-slate-600 max-w-5xl leading-relaxed">
                    Our company specializes in document preparatory work for Immigration Firms, Attorneys, and institutions that need assistance with drafting letters of recommendation, CV - Resume, business plans, testimonial letters, and other related documents for both Family Based and EB - Employment Based Visas EB1, EB2 NIW, EB3, EB5.
                </p>
            </div>

            <div class="grid lg:grid-cols-3 gap-12">
                <!-- Drafting -->
                <div class="service-card transition-all duration-300">
                    <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&q=80&w=400" alt="Drafting" class="w-full h-56 object-cover rounded-lg mb-6">
                    <h3 class="serif text-2xl text-ds-blue mb-4">Drafting</h3>
                    <ul class="space-y-2 text-slate-600 border-l-2 border-ds-blue pl-4">
                        <li>• Testimonial Letters</li>
                        <li>• Cover Letters</li>
                        <li>• CV - Resume</li>
                        <li>• Business Plans</li>
                        <li>• Experience Letters</li>
                    </ul>
                </div>

                <!-- Consulting -->
                <div class="service-card transition-all duration-300">
                    <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=400" alt="Consulting" class="w-full h-56 object-cover rounded-lg mb-6">
                    <h3 class="serif text-2xl text-ds-blue mb-4">Consulting</h3>
                    <ul class="space-y-2 text-slate-600 border-l-2 border-ds-blue pl-4">
                        <li>• Case Strategy</li>
                        <li>• Operations Advisory</li>
                        <li>• Workflow Mapping</li>
                        <li>• Proofreads, Editing</li>
                    </ul>
                </div>

                <div class="service-card transition-all duration-300">
                    <img src="https://images.unsplash.com/photo-1454165833767-027ffea9e77b?auto=format&fit=crop&q=80&w=400" alt="Translations" class="w-full h-56 object-cover rounded-lg mb-6">
                    <h3 class="serif text-2xl text-ds-blue mb-4">Translations</h3>
                    <p class="text-slate-600 border-l-2 border-ds-blue pl-4">
                        We translate documents in three main languages: English, Spanish, and Portuguese.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Us Section -->
    <section id="about" class="py-24 bg-slate-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <div class="w-full lg:w-1/2">
                    <div class="relative">
                        <div class="absolute -inset-4 bg-ds-blue opacity-10 rounded-lg"></div>
                        <img src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?auto=format&fit=crop&q=80" alt="Justice" class="relative rounded-lg shadow-xl w-full">
                    </div>
                </div>
                <div class="w-full lg:w-1/2">
                    <h2 class="serif text-4xl text-ds-blue mb-6">Who We Are</h2>
                    <p class="text-xl text-slate-600 leading-relaxed mb-8">
                        We aim to serve business professionals with document preparation services and assistance. Our goal is to be the background engine assisting you and your clients with all your document drafting needs.
                    </p>
                    <div class="p-6 bg-white rounded-lg shadow-sm border-l-4 border-ds-blue">
                        <h4 class="font-bold text-ds-blue mb-2">Our Promise</h4>
                        <p class="text-slate-600 text-sm">We approach each assignment with the same care and effort as if they were our very own. Confidentiality is assured.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Philosophy & Promise -->
    <section id="philosophy" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="serif text-4xl text-ds-blue mb-16">Our Philosophy</h2>
            <div class="grid md:grid-cols-3 gap-12">
                <div class="space-y-4">
                    <h3 class="serif text-2xl text-ds-blue">Quality</h3>
                    <p class="text-slate-600">Your clients are our clients. We approach each assignment with the same care and effort as if they were our very own.</p>
                </div>
                <div class="space-y-4">
                    <h3 class="serif text-2xl text-ds-blue">Efficiency</h3>
                    <p class="text-slate-600">Typical turn-around times are between 48-72 hours, depending on the scope of work. 24 Hour and Same Day service is also available.</p>
                </div>
                <div class="space-y-4">
                    <h3 class="serif text-2xl text-ds-blue">Fair Prices</h3>
                    <p class="text-slate-600">We provide the best work at the best price, staying within your budget while delivering top-tier legal drafting.</p>
                </div>
            </div>

            <!-- Promise Highlights -->
            <div class="mt-24 grid md:grid-cols-2 gap-12">
                <div class="flex gap-6 items-start bg-slate-50 p-8 rounded-xl">
                    <div class="w-16 h-16 bg-ds-blue/10 rounded-full flex items-center justify-center flex-shrink-0">
                        <svg class="w-8 h-8 text-ds-blue" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path></svg>
                    </div>
                    <div>
                        <h4 class="text-xl font-bold mb-2">Discreet</h4>
                        <p class="text-sm text-slate-500 font-bold uppercase tracking-widest mb-3">Confidentiality is Assured</p>
                        <p class="text-slate-600">We are not on social media, we do not want a social media presence. Our goal is to be in the background assisting you and your clients.</p>
                    </div>
                </div>
                <div class="flex gap-6 items-start bg-slate-50 p-8 rounded-xl">
                    <div class="w-16 h-16 bg-ds-blue/10 rounded-full flex items-center justify-center flex-shrink-0">
                        <svg class="w-8 h-8 text-ds-blue" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                    </div>
                    <div>
                        <h4 class="text-xl font-bold mb-2">Speed</h4>
                        <p class="text-sm text-slate-500 font-bold uppercase tracking-widest mb-3">Fast, reliable service</p>
                        <p class="text-slate-600">Our typical turnaround time for producing documents is 48-72 hours. 24 Hour and Same Day Service is also available.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Us Section -->
    <section id="contact" class="py-24 bg-ds-blue text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-2 gap-16">
                <div>
                    <h2 class="serif text-4xl mb-8">Contact Us</h2>
                    <p class="text-blue-100 mb-12">We are here to help. Reach out to us via phone, email, or visit our registered office.</p>
                    
                    <div class="space-y-8">
                        <div>
                            <h4 class="font-bold uppercase tracking-widest text-xs text-blue-200 mb-2">Phone</h4>
                            <p class="text-lg">Business Hours: <a href="tel:+13057977317" class="hover:text-blue-300 transition-colors">+1 (305) 797-7317</a></p>
                            <p class="text-lg">Weekend/After Hours: <a href="tel:+18643208814" class="hover:text-blue-300 transition-colors">+1 (864) 320-8814</a></p>
                        </div>
                        <div>
                            <h4 class="font-bold uppercase tracking-widest text-xs text-blue-200 mb-2">E-mail</h4>
                            <a href="mailto:info@dsdocs.com" class="text-lg hover:text-blue-300 transition-colors">info@dsdocs.com</a>
                        </div>
                        <div>
                            <h4 class="font-bold uppercase tracking-widest text-xs text-blue-200 mb-2">Registered Office Address</h4>
                            <p class="text-lg">Hammett Grove Ln Greer, SC 29650</p>
                        </div>
                        <div class="flex gap-6 pt-4">
                            <a href="#" class="p-3 bg-white/10 rounded hover:bg-white/20 transition-all"><svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl p-8 text-slate-800 shadow-2xl">
                    <form class="space-y-6">
                        <div>
                            <label class="block text-sm font-bold text-slate-700 mb-2">Name*</label>
                            <input type="text" class="w-full px-4 py-3 border border-slate-300 rounded focus:ring-2 focus:ring-ds-blue focus:border-ds-blue transition-all" required>
                        </div>
                        <div>
                            <label class="block text-sm font-bold text-slate-700 mb-2">Message*</label>
                            <textarea rows="6" class="w-full px-4 py-3 border border-slate-300 rounded focus:ring-2 focus:ring-ds-blue focus:border-ds-blue transition-all" required></textarea>
                        </div>
                        <p class="text-xs text-slate-400 font-medium italic">* Indicates required fields</p>
                        <button type="submit" class="w-full bg-[#e67e22] hover:bg-[#d35400] text-white font-bold py-4 rounded uppercase tracking-widest transition-all shadow-lg">Send</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 bg-white text-center border-t">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-center gap-2 mb-8">
                <span class="text-2xl font-bold tracking-tight text-ds-blue">DS<span class="font-light">Docs</span></span>
            </div>
            <nav class="flex flex-wrap justify-center gap-8 text-sm font-medium uppercase tracking-widest text-slate-500 mb-8">
                <a href="#home" class="hover:text-ds-blue">Home</a>
                <a href="#services" class="hover:text-ds-blue">Our Services</a>
                <a href="#about" class="hover:text-ds-blue">About Us</a>
                <a href="#philosophy" class="hover:text-ds-blue">Our Philosophy</a>
                <a href="#contact" class="hover:text-ds-blue">Contact Us</a>
            </nav>
            <p class="text-slate-400 text-xs">All rights reserved, DS Documents LLC.</p>
            <p class="text-slate-400 text-xs mt-2">© 2019 - 2024</p>
        </div>
    </footer>

    <script>
        const mobileBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Close menu when link is clicked
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });
    </script>
</body>
</html>

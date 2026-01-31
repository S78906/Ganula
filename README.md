```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Portal - Welcome</title>
    
    <!-- Fonts: Inter and Montserrat as requested -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- GSAP for smooth animations -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        'sans': ['Inter', 'sans-serif'],
                        'display': ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        primary: {
                            50: '#eff6ff',
                            100: '#dbeafe',
                            500: '#3b82f6',
                            600: '#2563eb',
                            700: '#1d4ed8',
                            900: '#1e3a8a',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }
        
        .font-display {
            font-family: 'Montserrat', sans-serif;
        }

        /* Animated Background */
        .hero-bg {
            background-image: 
                linear-gradient(135deg, rgba(30, 58, 138, 0.9) 0%, rgba(79, 70, 229, 0.85) 50%, rgba(147, 51, 234, 0.8) 100%),
                url('https://images.unsplash.com/photo-1523050854058-8df90110c9f1?q=80&w=2070&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-blend-mode: multiply;
        }

        /* Floating Orbs Animation */
        .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.4;
            animation: float 20s infinite ease-in-out;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -50px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Glassmorphism Card */
        .glass-card {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.18);
            box-shadow: 
                0 8px 32px 0 rgba(31, 38, 135, 0.37),
                inset 0 0 0 1px rgba(255, 255, 255, 0.1);
        }

        .glass-button {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .glass-button:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
            box-shadow: 0 10px 40px -10px rgba(255, 255, 255, 0.3);
        }

        .primary-button {
            background: linear-gradient(135deg, #3b82f6 0%, #8b5cf6 100%);
            box-shadow: 0 4px 20px rgba(59, 130, 246, 0.4);
        }

        .primary-button:hover {
            box-shadow: 0 8px 30px rgba(59, 130, 246, 0.6);
            transform: translateY(-2px);
        }

        /* Text Gradient */
        .text-gradient {
            background: linear-gradient(135deg, #ffffff 0%, #cbd5e1 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Decorative Grid */
        .grid-pattern {
            background-image: 
                linear-gradient(rgba(255, 255, 255, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
            background-size: 60px 60px;
            mask-image: radial-gradient(circle at center, black, transparent 80%);
        }

        /* Smooth reveal animation classes */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
        }
    </style>
</head>
<body class="antialiased text-slate-800">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 top-0 transition-all duration-300" id="navbar">
        <div class="glass-card border-b border-white/10 mx-4 mt-4 rounded-2xl px-6 py-4 max-w-7xl mx-auto">
            <div class="flex justify-between items-center">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-blue-500 to-purple-600 flex items-center justify-center text-white font-bold text-xl shadow-lg">
                        S
                    </div>
                    <span class="text-white font-display font-bold text-xl tracking-tight">StudentPortal</span>
                </div>
                
                <div class="hidden md:flex items-center gap-8">
                    <a href="#" class="text-white/80 hover:text-white transition-colors text-sm font-medium">Dashboard</a>
                    <a href="#" class="text-white/80 hover:text-white transition-colors text-sm font-medium">Resources</a>
                    <a href="#" class="text-white/80 hover:text-white transition-colors text-sm font-medium">Grades</a>
                    <a href="#" class="text-white/80 hover:text-white transition-colors text-sm font-medium">Calendar</a>
                </div>

                <div class="flex items-center gap-4">
                    <button class="hidden sm:block text-white/80 hover:text-white text-sm font-medium transition-colors">Sign In</button>
                    <button class="primary-button text-white px-6 py-2.5 rounded-xl text-sm font-semibold transition-all">
                        Get Started
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero-bg relative min-h-screen flex items-center justify-center px-4 overflow-hidden">
        
        <!-- Animated Background Elements -->
        <div class="absolute inset-0 grid-pattern opacity-30"></div>
        
        <!-- Floating Orbs -->
        <div class="orb w-96 h-96 bg-blue-500 top-0 left-0 -translate-x-1/2 -translate-y-1/2"></div>
        <div class="orb w-80 h-80 bg-purple-500 bottom-0 right-0 translate-x-1/3 translate-y-1/3 animation-delay-2000"></div>
        <div class="orb w-64 h-64 bg-indigo-400 top-1/2 right-1/4 opacity-20"></div>

        <!-- Main Content -->
        <div class="relative z-10 max-w-5xl mx-auto text-center pt-24">
            
            <!-- Glass Card Container -->
            <div class="glass-card rounded-3xl p-8 md:p-16 reveal" id="hero-card">
                
                <!-- Badge -->
                <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass-button text-white/90 text-xs font-semibold uppercase tracking-wider mb-8">
                    <span class="w-2 h-2 rounded-full bg-green-400 animate-pulse"></span>
                    Academic Year 2025-2026
                </div>

                <!-- Main Heading -->
                <h1 class="font-display font-black text-5xl md:text-7xl lg:text-8xl text-white mb-6 leading-tight tracking-tight text-gradient">
                    Welcome to the<br>
                    <span class="bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent">Student Portal</span>
                </h1>

                <!-- Mission Statement -->
                <p class="text-lg md:text-xl text-white/80 max-w-2xl mx-auto mb-10 leading-relaxed font-light">
                    Your gateway to academic excellence. Track your progress, access resources, and view your standings in real-time.
                </p>

                <!-- CTA Buttons -->
                <div class="flex flex-col sm:flex-row gap-4 justify-center items-center mb-12">
                    <button class="primary-button text-white px-8 py-4 rounded-2xl font-semibold text-lg flex items-center gap-2 group w-full sm:w-auto justify-center">
                        Access Dashboard
                        <i data-lucide="arrow-right" class="w-5 h-5 group-hover:translate-x-1 transition-transform"></i>
                    </button>
                    
                    <button class="glass-button text-white px-8 py-4 rounded-2xl font-semibold text-lg flex items-center gap-2 w-full sm:w-auto justify-center">
                        <i data-lucide="play-circle" class="w-5 h-5"></i>
                        Watch Demo
                    </button>
                </div>

                <!-- Stats Row -->
                <div class="grid grid-cols-2 md:grid-cols-4 gap-6 pt-8 border-t border-white/10">
                    <div class="text-center reveal-stat">
                        <div class="text-3xl font-display font-bold text-white mb-1">15k+</div>
                        <div class="text-white/60 text-sm">Active Students</div>
                    </div>
                    <div class="text-center reveal-stat">
                        <div class="text-3xl font-display font-bold text-white mb-1">98%</div>
                        <div class="text-white/60 text-sm">Satisfaction</div>
                    </div>
                    <div class="text-center reveal-stat">
                        <div class="text-3xl font-display font-bold text-white mb-1">500+</div>
                        <div class="text-white/60 text-sm">Resources</div>
                    </div>
                    <div class="text-center reveal-stat">
                        <div class="text-3xl font-display font-bold text-white mb-1">24/7</div>
                        <div class="text-white/60 text-sm">Support</div>
                    </div>
                </div>
            </div>

            <!-- Scroll Indicator -->
            <div class="absolute -bottom-12 left-1/2 -translate-x-1/2 text-white/40 animate-bounce">
                <i data-lucide="chevron-down" class="w-8 h-8"></i>
            </div>
        </div>
    </section>

    <!-- Quick Features Preview (Below Hero) -->
    <section class="bg-slate-50 py-20 px-4">
        <div class="max-w-7xl mx-auto">
            <div class="grid md:grid-cols-3 gap-8">
                <!-- Feature 1 -->
                <div class="bg-white rounded-2xl p-8 shadow-xl shadow-slate-200/50 border border-slate-100 hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-14 h-14 rounded-2xl bg-blue-100 text-blue-600 flex items-center justify-center mb-6">
                        <i data-lucide="trending-up" class="w-7 h-7"></i>
                    </div>
                    <h3 class="font-display font-bold text-xl mb-3 text-slate-900">Track Progress</h3>
                    <p class="text-slate-600 leading-relaxed">Real-time grade tracking and academic performance analytics at your fingertips.</p>
                </div>

                <!-- Feature 2 -->
                <div class="bg-white rounded-2xl p-8 shadow-xl shadow-slate-200/50 border border-slate-100 hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-14 h-14 rounded-2xl bg-purple-100 text-purple-600 flex items-center justify-center mb-6">
                        <i data-lucide="book-open" class="w-7 h-7"></i>
                    </div>
                    <h3 class="font-display font-bold text-xl mb-3 text-slate-900">Access Resources</h3>
                    <p class="text-slate-600 leading-relaxed">Library materials, course documents, and study resources all in one place.</p>
                </div>

                <!-- Feature 3 -->
                <div class="bg-white rounded-2xl p-8 shadow-xl shadow-slate-200/50 border border-slate-100 hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-14 h-14 rounded-2xl bg-indigo-100 text-indigo-600 flex items-center justify-center mb-6">
                        <i data-lucide="award" class="w-7 h-7"></i>
                    </div>
                    <h3 class="font-display font-bold text-xl mb-3 text-slate-900">View Standings</h3>
                    <p class="text-slate-600 leading-relaxed">Check your academic ranking and compare performance with anonymized cohort data.</p>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Initialize Lucide icons
        lucide.createIcons();

        // GSAP Animations
        window.addEventListener('load', () => {
            const tl = gsap.timeline();

            // Reveal hero card
            tl.to('#hero-card', {
                opacity: 1,
                y: 0,
                duration: 1.2,
                ease: 'power3.out'
            });

            // Stagger reveal stats
            tl.to('.reveal-stat', {
                opacity: 1,
                y: 0,
                duration: 0.8,
                stagger: 0.1,
                ease: 'power2.out'
            }, '-=0.6');

            // Animate orbs slowly
            gsap.to('.orb', {
                x: 'random(-50, 50)',
                y: 'random(-50, 50)',
                duration: 'random(10, 20)',
                repeat: -1,
                yoyo: true,
                ease: 'sine.inOut'
            });
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const nav = document.getElementById('navbar');
            if (window.scrollY > 50) {
                nav.classList.add('scale-[0.98]');
            } else {
                nav.classList.remove('scale-[0.98]');
            }
        });
    </script>
</body>
</html>
```

<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CAZPER | Web Developer & Frontend Specialist</title>
    <meta name="description" content="Portfolio of CAZPER - Creative Web Developer & Frontend Specialist">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Space+Grotesk:wght@300;500;700&display=swap" rel="stylesheet">
    
    <!-- Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Tailwind Configuration -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        mono: ['"JetBrains Mono"', 'monospace'],
                        sans: ['"Space Grotesk"', 'sans-serif'],
                    },
                    colors: {
                        cyber: {
                            black: '#050505',
                            dark: '#0a0a0f',
                            gray: '#1a1a2e',
                            cyan: '#00f3ff',
                            purple: '#bc13fe',
                            pink: '#ff0055',
                        }
                    },
                    animation: {
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'float': 'float 6s ease-in-out infinite',
                        'glow': 'glow 2s ease-in-out infinite alternate',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-20px)' },
                        },
                        glow: {
                            'from': { boxShadow: '0 0 10px #00f3ff, 0 0 20px #00f3ff' },
                            'to': { boxShadow: '0 0 20px #bc13fe, 0 0 30px #bc13fe' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #050505;
        }
        ::-webkit-scrollbar-thumb {
            background: #1a1a2e;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00f3ff;
        }

        /* Glitch Effect Base */
        .glitch-wrapper {
            position: relative;
        }
        
        /* Neon Text Utilities */
        .text-neon-cyan {
            text-shadow: 0 0 5px #00f3ff, 0 0 10px #00f3ff;
        }
        .text-neon-purple {
            text-shadow: 0 0 5px #bc13fe, 0 0 10px #bc13fe;
        }
        
        /* Card Hover Effects */
        .cyber-card {
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 243, 255, 0.1);
        }
        .cyber-card:hover {
            border-color: #00f3ff;
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.2);
            transform: translateY(-5px);
        }

        /* Custom Cursor */
        .cursor-dot,
        .cursor-outline {
            position: fixed;
            top: 0;
            left: 0;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            z-index: 9999;
            pointer-events: none;
        }
        .cursor-dot {
            width: 8px;
            height: 8px;
            background-color: #00f3ff;
        }
        .cursor-outline {
            width: 40px;
            height: 40px;
            border: 1px solid rgba(0, 243, 255, 0.5);
            transition: width 0.2s, height 0.2s, background-color 0.2s;
        }
        
        /* Scanline Overlay */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0,0,0,0.1) 50%,
                rgba(0,0,0,0.1)
            );
            background-size: 100% 4px;
            pointer-events: none;
            z-index: 50;
            opacity: 0.3;
        }

        /* Loader */
        #loader {
            position: fixed;
            inset: 0;
            background: #050505;
            z-index: 10000;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: opacity 0.5s ease;
        }
    </style>
<base target="_blank">
</head>
<body class="bg-cyber-black text-gray-300 font-sans overflow-x-hidden selection:bg-cyber-cyan selection:text-cyber-black">

    <!-- Custom Cursor Elements -->
    <div class="cursor-dot hidden md:block"></div>
    <div class="cursor-outline hidden md:block"></div>

    <!-- Scanline Effect -->
    <div class="scanlines"></div>

    <!-- Loader -->
    <div id="loader">
        <div class="text-cyber-cyan font-mono text-2xl animate-pulse">
            &lt;CAZPER /&gt;
        </div>
    </div>

    <!-- Navigation -->
    <nav class="fixed w-full z-40 top-0 transition-all duration-300" id="navbar">
        <div class="absolute inset-0 bg-cyber-black/80 backdrop-blur-md border-b border-white/5"></div>
        <div class="container mx-auto px-6 py-4 relative flex justify-between items-center">
            <a href="#" class="text-2xl font-bold font-mono text-white group">
                <span class="text-cyber-cyan">&lt;</span>CAZPER<span class="text-cyber-cyan">/&gt;</span>
            </a>
            
            <!-- Desktop Menu -->
            <div class="hidden md:flex space-x-8 font-mono text-sm">
                <a href="#home" class="hover:text-cyber-cyan transition-colors nav-link">[Home]</a>
                <a href="#about" class="hover:text-cyber-cyan transition-colors nav-link">[About]</a>
                <a href="#skills" class="hover:text-cyber-cyan transition-colors nav-link">[Skills]</a>
                <a href="#projects" class="hover:text-cyber-cyan transition-colors nav-link">[Projects]</a>
                <a href="#contact" class="hover:text-cyber-cyan transition-colors nav-link">[Contact]</a>
            </div>

            <!-- Mobile Menu Button -->
            <button id="mobile-menu-btn" class="md:hidden text-white hover:text-cyber-cyan">
                <i class="fas fa-bars text-2xl"></i>
            </button>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden bg-cyber-dark border-b border-cyber-cyan/20 absolute w-full">
            <div class="flex flex-col p-4 space-y-4 font-mono text-center">
                <a href="#home" class="mobile-link hover:text-cyber-cyan py-2">[Home]</a>
                <a href="#about" class="mobile-link hover:text-cyber-cyan py-2">[About]</a>
                <a href="#skills" class="mobile-link hover:text-cyber-cyan py-2">[Skills]</a>
                <a href="#projects" class="mobile-link hover:text-cyber-cyan py-2">[Projects]</a>
                <a href="#contact" class="mobile-link hover:text-cyber-cyan py-2">[Contact]</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex items-center justify-center relative overflow-hidden pt-20">
        <!-- Background Elements -->
        <div class="absolute inset-0 z-0">
            <div class="absolute top-20 left-10 w-72 h-72 bg-cyber-purple/20 rounded-full blur-[100px] animate-pulse-slow"></div>
            <div class="absolute bottom-20 right-10 w-96 h-96 bg-cyber-cyan/10 rounded-full blur-[120px] animate-pulse-slow" style="animation-delay: 1s;"></div>
        </div>

        <div class="container mx-auto px-6 z-10 grid md:grid-cols-2 gap-12 items-center">
            <div class="order-2 md:order-1">
                <div class="font-mono text-cyber-cyan mb-4 opacity-0 translate-y-10 animate-fade-in-up" style="animation-delay: 0.2s; animation-fill-mode: forwards;">
                    &lt;system.init&gt;
                </div>
                <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 leading-tight opacity-0 translate-y-10 animate-fade-in-up" style="animation-delay: 0.4s; animation-fill-mode: forwards;">
                    Hi, I'm <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyber-cyan to-cyber-purple typing-effect">CAZPER</span>
                </h1>
                <div class="h-8 mb-8">
                    <span id="typewriter" class="text-xl md:text-2xl text-gray-400 font-mono border-r-2 border-cyber-cyan pr-1"></span>
                </div>
                <p class="text-gray-400 mb-8 max-w-lg text-lg opacity-0 translate-y-10 animate-fade-in-up" style="animation-delay: 0.6s; animation-fill-mode: forwards;">
                    I craft responsive, high-performance web experiences with clean code and futuristic design. Turning complex problems into elegant digital solutions.
                </p>
                
                <div class="flex flex-wrap gap-4 opacity-0 translate-y-10 animate-fade-in-up" style="animation-delay: 0.8s; animation-fill-mode: forwards;">
                    <a href="#projects" class="group relative px-8 py-3 bg-transparent overflow-hidden rounded-none border border-cyber-cyan text-cyber-cyan font-mono hover:text-cyber-black transition-colors duration-300">
                        <span class="absolute inset-0 w-full h-full bg-cyber-cyan/0 group-hover:bg-cyber-cyan transition-all duration-300"></span>
                        <span class="relative flex items-center gap-2">
                            View Projects <i class="fas fa-arrow-right group-hover:translate-x-1 transition-transform"></i>
                        </span>
                    </a>
                    <a href="#contact" class="group px-8 py-3 border border-gray-700 text-gray-300 font-mono hover:border-cyber-purple hover:text-cyber-purple transition-all duration-300">
                        Contact Me
                    </a>
                </div>
            </div>

            <div class="order-1 md:order-2 flex justify-center relative opacity-0 animate-fade-in" style="animation-delay: 1s; animation-fill-mode: forwards;">
                <!-- Abstract Code Visualization -->
                <div class="relative w-80 h-80 md:w-96 md:h-96 animate-float">
                    <div class="absolute inset-0 border-2 border-cyber-cyan/30 rounded-full animate-[spin_10s_linear_infinite]"></div>
                    <div class="absolute inset-4 border-2 border-cyber-purple/30 rounded-full animate-[spin_15s_linear_infinite_reverse]"></div>
                    <div class="absolute inset-0 flex items-center justify-center">
                        <div class="text-6xl font-mono font-bold text-white/10 select-none">
                            &lt;/&gt;
                        </div>
                    </div>
                    <!-- Floating Code Snippets -->
                    <div class="absolute top-0 left-0 bg-cyber-gray/80 p-3 rounded border border-cyber-cyan/20 text-xs font-mono text-cyber-cyan backdrop-blur-sm shadow-[0_0_15px_rgba(0,243,255,0.1)]">
                        const future = "now";
                    </div>
                    <div class="absolute bottom-10 right-0 bg-cyber-gray/80 p-3 rounded border border-cyber-purple/20 text-xs font-mono text-cyber-purple backdrop-blur-sm shadow-[0_0_15px_rgba(188,19,254,0.1)]">
                        npm run build
                    </div>
                </div>
            </div>
        </div>

        <!-- Scroll Down Indicator -->
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
            <a href="#about" class="text-gray-500 hover:text-cyber-cyan transition-colors">
                <i class="fas fa-chevron-down text-2xl"></i>
            </a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 bg-cyber-dark relative">
        <div class="container mx-auto px-6">
            <div class="flex flex-col md:flex-row items-center gap-16">
                <div class="w-full md:w-1/2 relative group reveal-on-scroll">
                    <div class="absolute -inset-1 bg-gradient-to-r from-cyber-cyan to-cyber-purple rounded-lg blur opacity-25 group-hover:opacity-75 transition duration-1000 group-hover:duration-200"></div>
                    <div class="relative bg-cyber-gray p-8 rounded-lg border border-white/10">
                        <div class="font-mono text-sm text-cyber-cyan mb-4">// About.sys</div>
                        <h2 class="text-3xl font-bold text-white mb-6">Behind the Code</h2>
                        <p class="text-gray-400 mb-4 leading-relaxed">
                            I'm CAZPER, a frontend developer obsessed with the intersection of design and technology. My journey started with a curiosity for how things work on the web, which quickly evolved into a passion for building immersive digital experiences.
                        </p>
                        <p class="text-gray-400 mb-6 leading-relaxed">
                            I specialize in the JavaScript ecosystem, focusing on performance, accessibility, and that "wow" factor that makes users remember a website. When I'm not coding, I'm exploring new design trends or optimizing my development workflow.
                        </p>
                        <div class="flex gap-4">
                            <div class="text-center">
                                <span class="block text-2xl font-bold text-cyber-cyan counter" data-target="5">0</span>
                                <span class="text-xs text-gray-500 uppercase tracking-wider">Years Exp.</span>
                            </div>
                            <div class="w-px bg-gray-700"></div>
                            <div class="text-center">
                                <span class="block text-2xl font-bold text-cyber-purple counter" data-target="50">0</span>
                                <span class="text-xs text-gray-500 uppercase tracking-wider">Projects</span>
                            </div>
                            <div class="w-px bg-gray-700"></div>
                            <div class="text-center">
                                <span class="block text-2xl font-bold text-cyber-pink counter" data-target="100">0</span>
                                <span class="text-xs text-gray-500 uppercase tracking-wider">Commits</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="w-full md:w-1/2 reveal-on-scroll">
                    <div class="grid grid-cols-2 gap-4">
                        <div class="space-y-4 mt-8">
                            <div class="bg-cyber-gray/50 p-6 rounded border border-white/5 hover:border-cyber-cyan/50 transition-colors">
                                <i class="fas fa-code text-2xl text-cyber-cyan mb-3"></i>
                                <h3 class="text-white font-bold mb-1">Clean Code</h3>
                                <p class="text-sm text-gray-500">Maintainable & Scalable</p>
                            </div>
                            <div class="bg-cyber-gray/50 p-6 rounded border border-white/5 hover:border-cyber-purple/50 transition-colors">
                                <i class="fas fa-mobile-alt text-2xl text-cyber-purple mb-3"></i>
                                <h3 class="text-white font-bold mb-1">Responsive</h3>
                                <p class="text-sm text-gray-500">Mobile First Design</p>
                            </div>
                        </div>
                        <div class="space-y-4">
                            <div class="bg-cyber-gray/50 p-6 rounded border border-white/5 hover:border-cyber-pink/50 transition-colors">
                                <i class="fas fa-bolt text-2xl text-cyber-pink mb-3"></i>
                                <h3 class="text-white font-bold mb-1">Performance</h3>
                                <p class="text-sm text-gray-500">Optimized Speed</p>
                            </div>
                            <div class="bg-cyber-gray/50 p-6 rounded border border-white/5 hover:border-green-400/50 transition-colors">
                                <i class="fas fa-rocket text-2xl text-green-400 mb-3"></i>
                                <h3 class="text-white font-bold mb-1">Modern</h3>
                                <p class="text-sm text-gray-500">Latest Tech Stack</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-24 bg-cyber-black relative overflow-hidden">
        <!-- Decorative background grid -->
        <div class="absolute inset-0 bg-[linear-gradient(to_right,#80808012_1px,transparent_1px),linear-gradient(to_bottom,#80808012_1px,transparent_1px)] bg-[size:24px_24px]"></div>

        <div class="container mx-auto px-6 relative z-10">
            <div class="text-center mb-16 reveal-on-scroll">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Technical <span class="text-cyber-cyan">Arsenal</span></h2>
                <div class="w-20 h-1 bg-gradient-to-r from-cyber-cyan to-cyber-purple mx-auto"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Skill Card 1 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fab fa-html5 text-6xl text-orange-500"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">HTML5 & CSS3</h3>
                    <p class="text-gray-400 text-sm mb-4">Semantic markup, Flexbox, Grid, and modern styling techniques.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-orange-500 to-red-500 h-2 rounded-full" style="width: 0%" data-width="95%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">95% Proficiency</span>
                </div>

                <!-- Skill Card 2 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll" style="transition-delay: 100ms;">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fab fa-js text-6xl text-yellow-400"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">JavaScript (ES6+)</h3>
                    <p class="text-gray-400 text-sm mb-4">DOM manipulation, Async/Await, APIs, and functional programming.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-yellow-400 to-yellow-600 h-2 rounded-full" style="width: 0%" data-width="90%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">90% Proficiency</span>
                </div>

                <!-- Skill Card 3 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll" style="transition-delay: 200ms;">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fas fa-paint-brush text-6xl text-cyber-purple"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">UI/UX Design</h3>
                    <p class="text-gray-400 text-sm mb-4">Figma, User Research, Wireframing, and Prototyping.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-cyber-purple to-pink-500 h-2 rounded-full" style="width: 0%" data-width="85%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">85% Proficiency</span>
                </div>

                <!-- Skill Card 4 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fas fa-mobile-alt text-6xl text-cyber-cyan"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">Responsive Design</h3>
                    <p class="text-gray-400 text-sm mb-4">Mobile-first approach, Media Queries, and Cross-browser compatibility.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-cyber-cyan to-blue-500 h-2 rounded-full" style="width: 0%" data-width="98%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">98% Proficiency</span>
                </div>

                <!-- Skill Card 5 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll" style="transition-delay: 100ms;">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fas fa-wind text-6xl text-teal-400"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">Tailwind CSS</h3>
                    <p class="text-gray-400 text-sm mb-4">Utility-first CSS, Custom configurations, and Design Systems.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-teal-400 to-teal-600 h-2 rounded-full" style="width: 0%" data-width="92%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">92% Proficiency</span>
                </div>

                <!-- Skill Card 6 -->
                <div class="cyber-card bg-cyber-dark p-8 rounded-xl relative group reveal-on-scroll" style="transition-delay: 200ms;">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition-opacity">
                        <i class="fas fa-cube text-6xl text-blue-500"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 font-mono">Three.js / WebGL</h3>
                    <p class="text-gray-400 text-sm mb-4">3D web experiences, Shaders, and Interactive animations.</p>
                    <div class="w-full bg-gray-800 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-blue-500 to-indigo-600 h-2 rounded-full" style="width: 0%" data-width="75%"></div>
                    </div>
                    <span class="text-xs text-gray-500 font-mono">75% Proficiency</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-24 bg-cyber-dark">
        <div class="container mx-auto px-6">
            <div class="flex flex-col md:flex-row justify-between items-end mb-16 reveal-on-scroll">
                <div>
                    <h2 class="text-3xl md:text-4xl font-bold text-white mb-2">Featured <span class="text-cyber-purple">Projects</span></h2>
                    <p class="text-gray-400">Selected works from my portfolio</p>
                </div>
                <a href="#" class="hidden md:inline-flex items-center gap-2 text-cyber-cyan hover:text-white transition-colors font-mono mt-4 md:mt-0">
                    View Github <i class="fab fa-github"></i>
                </a>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Project 1 -->
                <article class="group bg-cyber-black rounded-xl overflow-hidden border border-white/5 hover:border-cyber-cyan/50 transition-all duration-300 hover:-translate-y-2 reveal-on-scroll">
                    <div class="relative h-48 overflow-hidden">
                        <div class="absolute inset-0 bg-cyber-cyan/20 group-hover:bg-transparent transition-colors z-10"></div>
                        <!-- Placeholder for project image -->
                        <div class="w-full h-full bg-gray-800 flex items-center justify-center group-hover:scale-110 transition-transform duration-500">
                            <i class="fas fa-chart-line text-4xl text-gray-600 group-hover:text-cyber-cyan transition-colors"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-xl font-bold text-white group-hover:text-cyber-cyan transition-colors">Nebula Dashboard</h3>
                            <div class="flex gap-2">
                                <i class="fab fa-react text-blue-400"></i>
                                <i class="fab fa-js text-yellow-400"></i>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-6">
                            A high-performance analytics dashboard featuring real-time data visualization, dark mode UI, and interactive charts using D3.js.
                        </p>
                        <div class="flex gap-4">
                            <a href="#" class="text-sm font-mono text-cyber-cyan hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-external-link-alt"></i> Live Demo
                            </a>
                            <a href="#" class="text-sm font-mono text-gray-500 hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-code"></i> Source
                            </a>
                        </div>
                    </div>
                </article>

                <!-- Project 2 -->
                <article class="group bg-cyber-black rounded-xl overflow-hidden border border-white/5 hover:border-cyber-purple/50 transition-all duration-300 hover:-translate-y-2 reveal-on-scroll" style="transition-delay: 100ms;">
                    <div class="relative h-48 overflow-hidden">
                        <div class="absolute inset-0 bg-cyber-purple/20 group-hover:bg-transparent transition-colors z-10"></div>
                        <div class="w-full h-full bg-gray-800 flex items-center justify-center group-hover:scale-110 transition-transform duration-500">
                            <i class="fas fa-shopping-bag text-4xl text-gray-600 group-hover:text-cyber-purple transition-colors"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-xl font-bold text-white group-hover:text-cyber-purple transition-colors">CyberStore</h3>
                            <div class="flex gap-2">
                                <i class="fab fa-vuejs text-green-400"></i>
                                <i class="fab fa-css3 text-blue-400"></i>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-6">
                            Full-stack e-commerce platform with headless CMS integration, Stripe payments, and a futuristic product customizer interface.
                        </p>
                        <div class="flex gap-4">
                            <a href="#" class="text-sm font-mono text-cyber-purple hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-external-link-alt"></i> Live Demo
                            </a>
                            <a href="#" class="text-sm font-mono text-gray-500 hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-code"></i> Source
                            </a>
                        </div>
                    </div>
                </article>

                <!-- Project 3 -->
                <article class="group bg-cyber-black rounded-xl overflow-hidden border border-white/5 hover:border-cyber-pink/50 transition-all duration-300 hover:-translate-y-2 reveal-on-scroll" style="transition-delay: 200ms;">
                    <div class="relative h-48 overflow-hidden">
                        <div class="absolute inset-0 bg-cyber-pink/20 group-hover:bg-transparent transition-colors z-10"></div>
                        <div class="w-full h-full bg-gray-800 flex items-center justify-center group-hover:scale-110 transition-transform duration-500">
                            <i class="fas fa-gamepad text-4xl text-gray-600 group-hover:text-cyber-pink transition-colors"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-xl font-bold text-white group-hover:text-cyber-pink transition-colors">Neon Drift</h3>
                            <div class="flex gap-2">
                                <i class="fab fa-html5 text-orange-500"></i>
                                <i class="fas fa-cube text-blue-500"></i>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-6">
                            Browser-based 3D racing game built with Three.js. Features procedural track generation, physics engine, and retro-wave aesthetics.
                        </p>
                        <div class="flex gap-4">
                            <a href="#" class="text-sm font-mono text-cyber-pink hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-external-link-alt"></i> Live Demo
                            </a>
                            <a href="#" class="text-sm font-mono text-gray-500 hover:text-white transition-colors flex items-center gap-1">
                                <i class="fas fa-code"></i> Source
                            </a>
                        </div>
                    </div>
                </article>
            </div>
            
            <div class="mt-12 text-center md:hidden">
                <a href="#" class="inline-flex items-center gap-2 text-cyber-cyan hover:text-white transition-colors font-mono">
                    View Github <i class="fab fa-github"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 bg-cyber-black relative">
        <div class="container mx-auto px-6">
            <div class="max-w-4xl mx-auto">
                <div class="text-center mb-16 reveal-on-scroll">
                    <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Initialize <span class="text-cyber-cyan">Contact</span></h2>
                    <p class="text-gray-400">Have a project in mind? Let's build the future together.</p>
                </div>

                <div class="grid md:grid-cols-3 gap-8">
                    <!-- Contact Info -->
                    <div class="md:col-span-1 space-y-6 reveal-on-scroll">
                        <div class="p-6 bg-cyber-dark rounded-lg border border-white/5 hover:border-cyber-cyan/30 transition-colors">
                            <div class="w-12 h-12 bg-cyber-cyan/10 rounded-full flex items-center justify-center mb-4 text-cyber-cyan">
                                <i class="fas fa-envelope text-xl"></i>
                            </div>
                            <h3 class="text-white font-bold mb-1">Email</h3>
                            <a href="mailto:hello@cazper.dev" class="text-gray-400 hover:text-cyber-cyan text-sm break-all">hello@cazper.dev</a>
                        </div>

                        <div class="p-6 bg-cyber-dark rounded-lg border border-white/5 hover:border-cyber-purple/30 transition-colors">
                            <div class="w-12 h-12 bg-cyber-purple/10 rounded-full flex items-center justify-center mb-4 text-cyber-purple">
                                <i class="fab fa-github text-xl"></i>
                            </div>
                            <h3 class="text-white font-bold mb-1">Github</h3>
                            <a href="#" class="text-gray-400 hover:text-cyber-purple text-sm">@cazper-dev</a>
                        </div>

                        <div class="p-6 bg-cyber-dark rounded-lg border border-white/5 hover:border-blue-500/30 transition-colors">
                            <div class="w-12 h-12 bg-blue-500/10 rounded-full flex items-center justify-center mb-4 text-blue-500">
                                <i class="fab fa-linkedin-in text-xl"></i>
                            </div>
                            <h3 class="text-white font-bold mb-1">LinkedIn</h3>
                            <a href="#" class="text-gray-400 hover:text-blue-500 text-sm">/in/cazper</a>
                        </div>
                    </div>

                    <!-- Contact Form -->
                    <div class="md:col-span-2 bg-cyber-dark p-8 rounded-lg border border-white/10 reveal-on-scroll">
                        <form id="contact-form" class="space-y-6">
                            <div class="grid md:grid-cols-2 gap-6">
                                <div class="relative">
                                    <input type="text" id="name" required class="peer w-full bg-cyber-black border border-gray-700 rounded px-4 py-3 text-white focus:outline-none focus:border-cyber-cyan focus:ring-1 focus:ring-cyber-cyan transition-all placeholder-transparent">
                                    <label for="name" class="absolute left-4 top-3 text-gray-500 text-sm transition-all peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-500 peer-placeholder-shown:top-3 peer-focus:-top-2.5 peer-focus:text-xs peer-focus:text-cyber-cyan peer-focus:bg-cyber-dark peer-focus:px-1 pointer-events-none">Name</label>
                                </div>
                                <div class="relative">
                                    <input type="email" id="email" required class="peer w-full bg-cyber-black border border-gray-700 rounded px-4 py-3 text-white focus:outline-none focus:border-cyber-cyan focus:ring-1 focus:ring-cyber-cyan transition-all placeholder-transparent">
                                    <label for="email" class="absolute left-4 top-3 text-gray-500 text-sm transition-all peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-500 peer-placeholder-shown:top-3 peer-focus:-top-2.5 peer-focus:text-xs peer-focus:text-cyber-cyan peer-focus:bg-cyber-dark peer-focus:px-1 pointer-events-none">Email</label>
                                </div>
                            </div>
                            <div class="relative">
                                <textarea id="message" rows="5" required class="peer w-full bg-cyber-black border border-gray-700 rounded px-4 py-3 text-white focus:outline-none focus:border-cyber-cyan focus:ring-1 focus:ring-cyber-cyan transition-all placeholder-transparent"></textarea>
                                <label for="message" class="absolute left-4 top-3 text-gray-500 text-sm transition-all peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-500 peer-placeholder-shown:top-3 peer-focus:-top-2.5 peer-focus:text-xs peer-focus:text-cyber-cyan peer-focus:bg-cyber-dark peer-focus:px-1 pointer-events-none">Message</label>
                            </div>
                            
                            <button type="submit" class="w-full bg-gradient-to-r from-cyber-cyan to-cyber-purple text-white font-bold py-4 rounded hover:opacity-90 transition-opacity flex items-center justify-center gap-2 group">
                                <span>Send Message</span>
                                <i class="fas fa-paper-plane group-hover:translate-x-1 transition-transform"></i>
                            </button>
                        </form>
                        
                        <!-- Success Message (Hidden by default) -->
                        <div id="success-message" class="hidden text-center py-10">
                            <div class="w-16 h-16 bg-green-500/20 rounded-full flex items-center justify-center mx-auto mb-4 text-green-500">
                                <i class="fas fa-check text-2xl"></i>
                            </div>
                            <h3 class="text-2xl font-bold text-white mb-2">Message Sent!</h3>
                            <p class="text-gray-400">I'll get back to you as soon as possible.</p>
                            <button id="reset-form" class="mt-6 text-cyber-cyan hover:underline">Send another</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-cyber-black border-t border-white/5 py-12">
        <div class="container mx-auto px-6">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-4 md:mb-0">
                    <span class="text-2xl font-bold font-mono text-white">
                        <span class="text-cyber-cyan">&lt;</span>CAZPER<span class="text-cyber-cyan">/&gt;</span>
                    </span>
                </div>
                
                <div class="flex space-x-6 mb-4 md:mb-0">
                    <a href="#" class="text-gray-400 hover:text-cyber-cyan transition-colors"><i class="fab fa-github text-xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-cyber-purple transition-colors"><i class="fab fa-twitter text-xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-blue-500 transition-colors"><i class="fab fa-linkedin text-xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-pink-500 transition-colors"><i class="fab fa-dribbble text-xl"></i></a>
                </div>
                
                <div class="text-gray-600 text-sm font-mono">
                    &copy; 2026 CAZPER. All rights reserved.
                </div>
            </div>
        </div>
    </footer>

    <script>
        // --- Loader ---
        window.addEventListener('load', () => {
            const loader = document.getElementById('loader');
            loader.style.opacity = '0';
            setTimeout(() => {
                loader.style.display = 'none';
            }, 500);
        });

        // --- Custom Cursor ---
        const cursorDot = document.querySelector('.cursor-dot');
        const cursorOutline = document.querySelector('.cursor-outline');

        window.addEventListener('mousemove', (e) => {
            const posX = e.clientX;
            const posY = e.clientY;

            // Dot follows immediately
            cursorDot.style.left = `${posX}px`;
            cursorDot.style.top = `${posY}px`;

            // Outline follows with slight delay (using animate for smoothness)
            cursorOutline.animate({
                left: `${posX}px`,
                top: `${posY}px`
            }, { duration: 500, fill: "forwards" });
        });

        // Add hover effect to interactive elements
        const interactiveElements = document.querySelectorAll('a, button, .cyber-card');
        interactiveElements.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursorOutline.style.width = '60px';
                cursorOutline.style.height = '60px';
                cursorOutline.style.backgroundColor = 'rgba(0, 243, 255, 0.1)';
            });
            el.addEventListener('mouseleave', () => {
                cursorOutline.style.width = '40px';
                cursorOutline.style.height = '40px';
                cursorOutline.style.backgroundColor = 'transparent';
            });
        });

        // --- Typewriter Effect ---
        const words = ["Frontend Specialist", "UI/UX Enthusiast", "Creative Developer", "Problem Solver"];
        let i = 0;
        let timer;

        function typeWriter() {
            const heading = document.getElementById("typewriter");
            const word = words[i];
            let currentText = heading.innerText;
            
            if (!this.isDeleting && currentText !== word) {
                heading.innerText = word.substring(0, currentText.length + 1);
                timer = setTimeout(typeWriter, 100);
            } else if (!this.isDeleting && currentText === word) {
                this.isDeleting = true;
                timer = setTimeout(typeWriter, 2000); // Pause at end
            } else if (this.isDeleting && currentText !== "") {
                heading.innerText = word.substring(0, currentText.length - 1);
                timer = setTimeout(typeWriter, 50);
            } else {
                this.isDeleting = false;
                i = (i + 1) % words.length;
                timer = setTimeout(typeWriter, 500);
            }
        }
        
        // Start typewriter after initial load
        setTimeout(typeWriter, 1000);

        // --- Mobile Menu Toggle ---
        const btn = document.getElementById('mobile-menu-btn');
        const menu = document.getElementById('mobile-menu');

        btn.addEventListener('click', () => {
            menu.classList.toggle('hidden');
        });

        // Close mobile menu when link is clicked
        document.querySelectorAll('.mobile-link').forEach(link => {
            link.addEventListener('click', () => {
                menu.classList.add('hidden');
            });
        });

        // --- Scroll Animations (Intersection Observer) ---
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-fade-in-up');
                    entry.target.style.opacity = "1";
                    
                    // Animate skill bars if inside
                    const skillBars = entry.target.querySelectorAll('.skill-bar');
                    skillBars.forEach(bar => {
                        bar.style.width = bar.getAttribute('data-width');
                        bar.style.transition = "width 1.5s ease-out";
                    });

                    // Animate counters
                    const counters = entry.target.querySelectorAll('.counter');
                    counters.forEach(counter => {
                        const target = +counter.getAttribute('data-target');
                        const duration = 2000; // ms
                        const increment = target / (duration / 16);
                        
                        let current = 0;
                        const updateCounter = () => {
                            current += increment;
                            if (current < target) {
                                counter.innerText = Math.ceil(current);
                                requestAnimationFrame(updateCounter);
                            } else {
                                counter.innerText = target + "+";
                            }
                        };
                        updateCounter();
                    });

                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal-on-scroll').forEach((el) => {
            el.style.opacity = "0";
            observer.observe(el);
        });

        // --- Navbar Scroll Effect ---
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('shadow-lg');
                navbar.querySelector('.absolute').classList.add('bg-cyber-black/95');
            } else {
                navbar.classList.remove('shadow-lg');
                navbar.querySelector('.absolute').classList.remove('bg-cyber-black/95');
            }
        });

        // --- Contact Form Handling ---
        const form = document.getElementById('contact-form');
        const successMsg = document.getElementById('success-message');
        const resetBtn = document.getElementById('reset-form');

        form.addEventListener('submit', (e) => {
            e.preventDefault();
            // Simulate sending
            const btn = form.querySelector('button');
            const originalText = btn.innerHTML;
            btn.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Sending...';
            btn.disabled = true;

            setTimeout(() => {
                form.style.display = 'none';
                successMsg.classList.remove('hidden');
                successMsg.classList.add('animate-fade-in');
                btn.innerHTML = originalText;
                btn.disabled = false;
                form.reset();
            }, 1500);
        });

        resetBtn.addEventListener('click', () => {
            successMsg.classList.add('hidden');
            form.style.display = 'block';
            form.classList.add('animate-fade-in');
        });

        // --- Smooth Scroll for Anchor Links ---
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add custom animation classes dynamically
        const style = document.createElement('style');
        style.innerHTML = `
            @keyframes fadeInUp {
                from {
                    opacity: 0;
                    transform: translate3d(0, 40px, 0);
                }
                to {
                    opacity: 1;
                    transform: translate3d(0, 0, 0);
                }
            }
            .animate-fade-in-up {
                animation: fadeInUp 0.8s ease-out forwards;
            }
            @keyframes fadeIn {
                from { opacity: 0; }
                to { opacity: 1; }
            }
            .animate-fade-in {
                animation: fadeIn 0.8s ease-out forwards;
            }
        `;
        document.head.appendChild(style);

    </script>
</body>
</html>

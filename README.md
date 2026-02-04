# SHIFTLY-MOTORS
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shiftly Motors | Tu próximo destino</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --azul-oscuro: #0F172A;
            --azul-claro: #38BDF8;
            --gris-marca: #64748B;
            --gris-claro: #F1F5F9;
        }

        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
            background-color: white;
        }

        h1, h2, h3, .font-montserrat {
            font-family: 'Montserrat', sans-serif;
        }

        /* Hero Section Animation */
        .hero-gradient {
            background: linear-gradient(135deg, rgba(15, 23, 42, 0.95) 0%, rgba(15, 23, 42, 0.8) 100%);
        }

        /* Mapa Interactivo */
        .region {
            transition: all 0.3s ease;
            cursor: pointer;
            stroke: #ffffff;
            stroke-width: 1;
        }
        
        .zone-1 { fill: #7DD3FC; } /* Azul Muy Claro */
        .zone-2 { fill: #38BDF8; } /* Azul Claro */
        .zone-3 { fill: #1E40AF; } /* Azul Oscuro */
        .zone-4 { fill: #94A3B8; } /* Gris Marca */

        .region:hover {
            filter: brightness(1.2);
            transform: scale(1.01);
        }

        /* Glassmorphism */
        .glass {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .car-card:hover img {
            transform: scale(1.05);
        }

        /* Logo custom animation */
        .logo-shift {
            transition: transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .logo-container:hover .logo-shift {
            transform: translateX(10px);
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav class="fixed w-full z-50 bg-white/80 backdrop-blur-md border-b border-slate-100">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <div class="flex items-center gap-2 logo-container cursor-pointer">
                <svg width="40" height="40" viewBox="0 0 100 100" class="logo-shift">
                    <path d="M20 50 L80 50 M80 50 L65 35 M80 50 L65 65" stroke="#0F172A" stroke-width="8" fill="none" stroke-linecap="round"/>
                    <circle cx="20" cy="50" r="8" fill="#38BDF8"/>
                </svg>
                <span class="text-2xl font-800 tracking-tighter text-slate-900 font-montserrat">SHIFTLY<span class="text-sky-500">MOTORS</span></span>
            </div>
            
            <div class="hidden md:flex gap-8 font-semibold text-sm uppercase tracking-wider text-slate-600">
                <a href="#inicio" class="hover:text-sky-500 transition">Inicio</a>
                <a href="#stock" class="hover:text-sky-500 transition">Vehículos</a>
                <a href="#zonas" class="hover:text-sky-500 transition">Zonas</a>
                <a href="#empleo" class="text-sky-600 hover:text-sky-700 transition font-bold">Viaja con nosotros</a>
            </div>

            <button class="bg-slate-900 text-white px-6 py-2 rounded-full font-bold hover:bg-sky-600 transition duration-300">
                Vender mi coche
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="inicio" class="relative h-screen flex items-center overflow-hidden">
        <div class="absolute inset-0 z-0">
            <img src="https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?auto=format&fit=crop&q=80&w=2000" class="w-full h-full object-cover" alt="Coche deportivo de lujo">
            <div class="absolute inset-0 hero-gradient"></div>
        </div>

        <div class="relative z-10 max-w-7xl mx-auto px-6 w-full text-white">
            <div class="max-w-2xl">
                <span class="inline-block bg-sky-500/20 text-sky-400 px-4 py-1 rounded-full text-sm font-bold mb-6 border border-sky-500/30">Líderes en Selección Premium</span>
                <h1 class="text-6xl md:text-8xl font-800 mb-8 leading-tight font-montserrat">
                    ¿Y si tu próximo destino <span class="text-sky-400">empieza</span> con un coche?
                </h1>
                <p class="text-xl text-slate-300 mb-10 font-light leading-relaxed">
                    En Shiftly Motors no vendemos solo coches de segunda mano; entregamos el primer paso de tu próxima gran aventura. Calidad certificada y transparencia total.
                </p>
                <div class="flex flex-wrap gap-4">
                    <a href="#stock" class="bg-sky-500 hover:bg-sky-400 text-slate-900 px-8 py-4 rounded-xl font-bold transition flex items-center gap-2">
                        Explorar Stock <i class="fa-solid fa-arrow-right"></i>
                    </a>
                    <a href="#zonas" class="glass px-8 py-4 rounded-xl font-bold hover:bg-white/20 transition">
                        Ver Cobertura
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Zonas de Actuación (Mapa) -->
    <section id="zonas" class="py-24 bg-slate-50">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl font-800 text-slate-900 mb-4 font-montserrat">Nuestra Presencia</h2>
                <p class="text-slate-500 max-w-2xl mx-auto">Operamos en todo el territorio nacional, divididos en 4 zonas logísticas estratégicas para garantizar la entrega más rápida de España.</p>
            </div>

            <div class="grid lg:grid-cols-2 gap-12 items-center">
                <!-- Mapa SVG Simplificado -->
                <div class="bg-white p-8 rounded-3xl shadow-xl shadow-slate-200">
                    <svg viewBox="0 0 1000 800" class="w-full h-auto drop-shadow-2xl">
                        <!-- Simplificación de España por Zonas -->
                        <!-- Zona 1: Norte -->
                        <path class="region zone-1" d="M150 100 L550 100 L550 200 L150 200 Z" /> 
                        <!-- Zona 2: Este -->
                        <path class="region zone-2" d="M550 100 L850 100 L850 500 L550 500 Z" />
                        <!-- Zona 3: Centro -->
                        <path class="region zone-3" d="M300 200 L550 200 L550 500 L300 500 Z" />
                        <!-- Zona 4: Sur -->
                        <path class="region zone-4" d="M150 500 L850 500 L850 750 L150 750 Z" />
                        
                        <!-- Etiquetas visuales en el mapa -->
                        <text x="350" y="150" fill="white" font-weight="bold" font-size="24">ZONA 1</text>
                        <text x="700" y="300" fill="white" font-weight="bold" font-size="24">ZONA 2</text>
                        <text x="425" y="350" fill="white" font-weight="bold" font-size="24">ZONA 3</text>
                        <text x="500" y="625" fill="white" font-weight="bold" font-size="24">ZONA 4</text>
                    </svg>
                </div>

                <!-- Lista de Zonas -->
                <div class="space-y-6">
                    <div class="flex items-start gap-4 p-6 bg-white rounded-2xl border-l-8 border-sky-300 shadow-sm">
                        <div class="bg-sky-100 text-sky-600 w-10 h-10 rounded-full flex items-center justify-center shrink-0 font-bold">1</div>
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Zona Norte</h3>
                            <p class="text-sm text-slate-500">Galicia, Asturias, Cantabria, País Vasco, Navarra, La Rioja</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4 p-6 bg-white rounded-2xl border-l-8 border-sky-400 shadow-sm">
                        <div class="bg-sky-100 text-sky-600 w-10 h-10 rounded-full flex items-center justify-center shrink-0 font-bold">2</div>
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Zona Levante y Aragón</h3>
                            <p class="text-sm text-slate-500">Aragón, Cataluña, Islas Baleares, Comunidad Valenciana</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4 p-6 bg-white rounded-2xl border-l-8 border-blue-800 shadow-sm">
                        <div class="bg-blue-100 text-blue-800 w-10 h-10 rounded-full flex items-center justify-center shrink-0 font-bold">3</div>
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Zona Centro</h3>
                            <p class="text-sm text-slate-500">Castilla y León, Comunidad de Madrid, Castilla La Mancha</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4 p-6 bg-white rounded-2xl border-l-8 border-slate-400 shadow-sm">
                        <div class="bg-slate-100 text-slate-600 w-10 h-10 rounded-full flex items-center justify-center shrink-0 font-bold">4</div>
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Zona Sur e Islas</h3>
                            <p class="text-sm text-slate-500">Extremadura, Andalucía, Murcia, Canarias</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Stock -->
    <section id="stock" class="py-24">
        <div class="max-w-7xl mx-auto px-6">
            <div class="flex justify-between items-end mb-12">
                <div>
                    <h2 class="text-4xl font-800 text-slate-900 font-montserrat">Recién llegados</h2>
                    <p class="text-slate-500">Unidades limitadas con certificación Shiftly 300+</p>
                </div>
                <button class="text-sky-600 font-bold hover:underline">Ver todo el catálogo <i class="fa-solid fa-chevron-right ml-1"></i></button>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <!-- Car Card 1 -->
                <div class="group car-card bg-white rounded-3xl overflow-hidden border border-slate-100 shadow-lg hover:shadow-2xl transition duration-500">
                    <div class="relative h-64 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1555353540-64580b51c258?auto=format&fit=crop&q=80&w=800" class="w-full h-full object-cover transition duration-500" alt="Coche">
                        <div class="absolute top-4 left-4 bg-white/90 px-3 py-1 rounded-lg text-xs font-bold text-slate-900">2022 • 25.000 km</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-slate-900 mb-2">SUV Luxury Edition</h3>
                        <p class="text-slate-500 text-sm mb-4">Híbrido • Automático • Techo Solar</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-800 text-slate-900">32.900€</span>
                            <button class="bg-slate-100 p-3 rounded-xl hover:bg-sky-500 hover:text-white transition"><i class="fa-solid fa-eye"></i></button>
                        </div>
                    </div>
                </div>
                <!-- Car Card 2 -->
                <div class="group car-card bg-white rounded-3xl overflow-hidden border border-slate-100 shadow-lg hover:shadow-2xl transition duration-500">
                    <div class="relative h-64 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1583121274602-3e2820c69888?auto=format&fit=crop&q=80&w=800" class="w-full h-full object-cover transition duration-500" alt="Coche">
                        <div class="absolute top-4 left-4 bg-white/90 px-3 py-1 rounded-lg text-xs font-bold text-slate-900">2023 • 5.000 km</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-slate-900 mb-2">Sport GT Pro</h3>
                        <p class="text-slate-500 text-sm mb-4">Gasolina • 350 CV • Cuero Nappa</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-800 text-slate-900">58.400€</span>
                            <button class="bg-slate-100 p-3 rounded-xl hover:bg-sky-500 hover:text-white transition"><i class="fa-solid fa-eye"></i></button>
                        </div>
                    </div>
                </div>
                <!-- Car Card 3 -->
                <div class="group car-card bg-white rounded-3xl overflow-hidden border border-slate-100 shadow-lg hover:shadow-2xl transition duration-500">
                    <div class="relative h-64 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?auto=format&fit=crop&q=80&w=800" class="w-full h-full object-cover transition duration-500" alt="Coche">
                        <div class="absolute top-4 left-4 bg-white/90 px-3 py-1 rounded-lg text-xs font-bold text-slate-900">2021 • 42.000 km</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-slate-900 mb-2">City Electric Compact</h3>
                        <p class="text-slate-500 text-sm mb-4">Eléctrico • 400km Autonomía</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-800 text-slate-900">21.500€</span>
                            <button class="bg-slate-100 p-3 rounded-xl hover:bg-sky-500 hover:text-white transition"><i class="fa-solid fa-eye"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Employer Branding: Viaja con nosotros -->
    <section id="empleo" class="py-24 bg-slate-900 text-white overflow-hidden relative">
        <div class="absolute top-0 right-0 w-1/3 h-full bg-sky-500/10 skew-x-12 transform translate-x-1/2"></div>
        
        <div class="max-w-7xl mx-auto px-6 relative z-10">
            <div class="grid lg:grid-cols-2 gap-16 items-center">
                <div>
                    <span class="text-sky-400 font-bold tracking-widest uppercase text-sm">Employer Branding</span>
                    <h2 class="text-5xl font-800 my-6 font-montserrat">Viaja con nosotros</h2>
                    <p class="text-slate-400 text-lg mb-8">
                        En Shiftly Motors no buscamos empleados, buscamos copilotos. Si te apasiona el mundo del motor y quieres revolucionar la forma en que la gente encuentra su próximo destino, este es tu sitio.
                    </p>
                    
                    <div class="space-y-6 mb-10">
                        <div class="flex gap-4">
                            <div class="w-12 h-12 bg-white/10 rounded-xl flex items-center justify-center text-sky-400"><i class="fa-solid fa-earth-europe"></i></div>
                            <div>
                                <h4 class="font-bold">Crecimiento sin fronteras</h4>
                                <p class="text-slate-500 text-sm">Forma parte de una red en expansión por toda España.</p>
                            </div>
                        </div>
                        <div class="flex gap-4">
                            <div class="w-12 h-12 bg-white/10 rounded-xl flex items-center justify-center text-sky-400"><i class="fa-solid fa-bolt"></i></div>
                            <div>
                                <h4 class="font-bold">Cultura de Alto Rendimiento</h4>
                                <p class="text-slate-500 text-sm">Trabajamos con tecnología punta y procesos ágiles.</p>
                            </div>
                        </div>
                    </div>

                    <button class="border-2 border-white/20 hover:border-sky-500 px-8 py-3 rounded-full transition font-bold">Ver Cultura Corporativa</button>
                </div>

                <div class="bg-white/5 p-8 rounded-3xl border border-white/10 backdrop-blur-sm">
                    <h3 class="text-2xl font-bold mb-6 flex items-center gap-3">
                        <i class="fa-solid fa-briefcase text-sky-500"></i> Ofertas en ruta
                    </h3>
                    
                    <div class="space-y-4">
                        <!-- Job 1 -->
                        <div class="p-5 rounded-2xl bg-white/5 hover:bg-white/10 border border-transparent hover:border-sky-500/50 transition cursor-pointer">
                            <div class="flex justify-between items-start mb-2">
                                <h5 class="font-bold text-lg">Asesor Comercial Senior</h5>
                                <span class="text-xs bg-sky-500/20 text-sky-400 px-2 py-1 rounded">Zona 3 - Madrid</span>
                            </div>
                            <p class="text-sm text-slate-400">Si los coches son tu lenguaje y el cliente tu prioridad, te queremos en el equipo.</p>
                        </div>
                        <!-- Job 2 -->
                        <div class="p-5 rounded-2xl bg-white/5 hover:bg-white/10 border border-transparent hover:border-sky-500/50 transition cursor-pointer">
                            <div class="flex justify-between items-start mb-2">
                                <h5 class="font-bold text-lg">Técnico de Certificación</h5>
                                <span class="text-xs bg-sky-500/20 text-sky-400 px-2 py-1 rounded">Zona 2 - Barcelona</span>
                            </div>
                            <p class="text-sm text-slate-400">Buscamos obsesionados con el detalle mecánico para nuestro centro de revisión.</p>
                        </div>
                        <!-- Job 3 -->
                        <div class="p-5 rounded-2xl bg-white/5 hover:bg-white/10 border border-transparent hover:border-sky-500/50 transition cursor-pointer">
                            <div class="flex justify-between items-start mb-2">
                                <h5 class="font-bold text-lg">Digital Marketing Manager</h5>
                                <span class="text-xs bg-sky-500/20 text-sky-400 px-2 py-1 rounded">Remoto / Híbrido</span>
                            </div>
                            <p class="text-sm text-slate-400">Ayúdanos a llevar el mensaje de Shiftly a cada pantalla del país.</p>
                        </div>
                    </div>
                    
                    <button class="w-full mt-8 bg-sky-500 hover:bg-sky-400 text-slate-900 py-4 rounded-xl font-800 transition uppercase tracking-wider text-sm">
                        Enviar candidatura espontánea
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-slate-50 pt-20 pb-10 border-t border-slate-200">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid md:grid-cols-4 gap-12 mb-16">
                <div class="col-span-1 md:col-span-1">
                    <div class="flex items-center gap-2 mb-6">
                        <svg width="30" height="30" viewBox="0 0 100 100">
                            <path d="M20 50 L80 50 M80 50 L65 35 M80 50 L65 65" stroke="#0F172A" stroke-width="12" fill="none"/>
                        </svg>
                        <span class="text-xl font-800 tracking-tighter text-slate-900 font-montserrat">SHIFTLY</span>
                    </div>
                    <p class="text-slate-500 text-sm leading-relaxed">
                        Redefiniendo el mercado de ocasión con tecnología, transparencia y pasión por el asfalto.
                    </p>
                </div>
                
                <div>
                    <h6 class="font-bold text-slate-900 mb-6">Explorar</h6>
                    <ul class="text-slate-500 text-sm space-y-4">
                        <li><a href="#" class="hover:text-sky-500">Stock Vehículos</a></li>
                        <li><a href="#" class="hover:text-sky-500">Coches Eléctricos</a></li>
                        <li><a href="#" class="hover:text-sky-500">Vender mi Coche</a></li>
                        <li><a href="#" class="hover:text-sky-500">Financiación</a></li>
                    </ul>
                </div>

                <div>
                    <h6 class="font-bold text-slate-900 mb-6">Compañía</h6>
                    <ul class="text-slate-500 text-sm space-y-4">
                        <li><a href="#" class="hover:text-sky-500">Sobre nosotros</a></li>
                        <li><a href="#" class="hover:text-sky-500">Zonas de actuación</a></li>
                        <li><a href="#empleo" class="hover:text-sky-500">Empleo</a></li>
                        <li><a href="#" class="hover:text-sky-500">Blog Motor</a></li>
                    </ul>
                </div>

                <div>
                    <h6 class="font-bold text-slate-900 mb-6">Síguenos</h6>
                    <div class="flex gap-4">
                        <a href="#" class="w-10 h-10 rounded-full bg-white border border-slate-200 flex items-center justify-center hover:bg-sky-500 hover:text-white transition"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white border border-slate-200 flex items-center justify-center hover:bg-sky-500 hover:text-white transition"><i class="fa-brands fa-linkedin"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white border border-slate-200 flex items-center justify-center hover:bg-sky-500 hover:text-white transition"><i class="fa-brands fa-x-twitter"></i></a>
                    </div>
                    <p class="mt-6 text-xs text-slate-400">Suscríbete para alertas de stock exclusivo.</p>
                </div>
            </div>
            
            <div class="pt-8 border-t border-slate-200 flex flex-col md:flex-row justify-between items-center gap-4 text-xs text-slate-400">
                <p>&copy; 2025 Shiftly Motors S.L. Todos los derechos reservados.</p>
                <div class="flex gap-6">
                    <a href="#">Privacidad</a>
                    <a href="#">Cookies</a>
                    <a href="#">Aviso Legal</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Interacción simple para el mapa
        document.querySelectorAll('.region').forEach(region => {
            region.addEventListener('click', function() {
                const zone = this.getAttribute('class').split(' ')[1];
                console.log("Seleccionada: " + zone);
                // Aquí podrías filtrar el stock por zona automáticamente
            });
        });

        // Animación suave de scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>

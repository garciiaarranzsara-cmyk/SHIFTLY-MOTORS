# SHIFTLY-MOTORS
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shiftly Motors | Tu Destino Empieza Aquí</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --azul-oscuro: #0F172A;
            --azul-claro: #38BDF8;
            --gris-marca: #64748B;
        }
        body { font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        h1, h2, h3, .font-montserrat { font-family: 'Montserrat', sans-serif; }

        /* Capas de subpáginas */
        .page-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: white; z-index: 100; display: none;
            overflow-y: auto; opacity: 0; transform: translateY(30px);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .page-overlay.active { display: block; opacity: 1; transform: translateY(0); }

        /* Estilos del Portal Privado */
        .portal-bg { background-color: #0F172A; color: white; }
        .kpi-card { 
            background: rgba(255,255,255,0.05); 
            border: 1px solid rgba(255,255,255,0.1); 
            border-radius: 1.5rem; 
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .kpi-card:hover { background: rgba(255,255,255,0.08); border-color: #38BDF8; }
        .kpi-card.selected { background: rgba(56, 189, 248, 0.15); border-color: #38BDF8; }

        .check-circle {
            width: 24px; height: 24px; border: 2px solid rgba(255,255,255,0.3);
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
            transition: all 0.3s;
        }
        .kpi-card.selected .check-circle { background: #38BDF8; border-color: #38BDF8; }
    </style>
</head>
<body class="bg-white text-slate-900">

    <!-- NAVBAR -->
    <nav class="fixed w-full z-50 bg-white/90 backdrop-blur-md border-b border-slate-100 h-20">
        <div class="max-w-7xl mx-auto px-6 h-full flex items-center justify-between">
            <!-- Logo con acceso a LinkedIn -->
            <a href="https://www.linkedin.com/company/shiftly-motors" target="_blank" class="flex items-center gap-2 group">
                <div class="relative">
                    <svg width="40" height="40" viewBox="0 0 100 100" class="group-hover:rotate-12 transition-transform">
                        <path d="M20 50 L80 50 M80 50 L65 35 M80 50 L65 65" stroke="#0F172A" stroke-width="8" fill="none" stroke-linecap="round"/>
                        <circle cx="20" cy="50" r="8" fill="#38BDF8"/>
                    </svg>
                    <div class="absolute -top-1 -right-1 bg-blue-600 text-white rounded-full w-4 h-4 flex items-center justify-center text-[10px]">
                        <i class="fa-brands fa-linkedin-in"></i>
                    </div>
                </div>
                <span class="text-2xl font-800 tracking-tighter font-montserrat uppercase">Shiftly<span class="text-sky-500">Motors</span></span>
            </a>

            <div class="hidden md:flex items-center gap-8">
                <a href="#stock" class="font-semibold text-sm hover:text-sky-500">STOCK</a>
                <a href="#zonas" class="font-semibold text-sm hover:text-sky-500">ZONAS</a>
                <button onclick="openPage('login')" class="bg-slate-900 text-white px-6 py-2 rounded-full text-sm font-bold hover:bg-sky-600 transition">
                    <i class="fa-solid fa-lock mr-2"></i> ACCESO EMPRESA
                </button>
            </div>
        </div>
    </nav>

    <!-- MAIN VIEW -->
    <main>
        <!-- Hero Section -->
        <section class="h-screen relative flex items-center justify-center text-center px-6 overflow-hidden">
            <div class="absolute inset-0 z-0">
                <img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&q=80&w=2000" class="w-full h-full object-cover grayscale-[20%]" alt="Coche">
                <div class="absolute inset-0 bg-slate-900/70"></div>
            </div>
            <div class="relative z-10 max-w-4xl text-white">
                <h1 class="text-5xl md:text-7xl font-800 mb-8 font-montserrat leading-tight">
                    ¿Y si tu próximo destino <span class="text-sky-400">empieza</span> con un coche?
                </h1>
                <p class="text-xl text-slate-300 mb-10 font-light">En Shiftly Motors redefinimos la confianza en el mercado de ocasión.</p>
                <div class="flex flex-wrap justify-center gap-4">
                    <a href="#stock" class="bg-sky-500 text-slate-900 px-10 py-4 rounded-xl font-bold hover:bg-sky-400 transition">Ver Vehículos</a>
                    <button onclick="openPage('login')" class="bg-white/10 backdrop-blur-md border border-white/20 px-10 py-4 rounded-xl font-bold hover:bg-white/20 transition">Portal Empleado</button>
                </div>
            </div>
        </section>

        <!-- Stock de Coches -->
        <section id="stock" class="py-24 bg-white">
            <div class="max-w-7xl mx-auto px-6">
                <h2 class="text-3xl font-800 mb-12 font-montserrat">Stock Destacado</h2>
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Coche 1 -->
                    <div class="group cursor-pointer bg-slate-50 rounded-3xl overflow-hidden shadow-sm hover:shadow-xl transition" 
                         onclick="openCar('Porsche 911 Carrera', 'https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&q=80&w=800', '135.000€', '450 CV • 2022')">
                        <div class="h-64 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&q=80&w=800" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-bold">Porsche 911 Carrera</h3>
                            <p class="text-slate-500 text-sm mb-4">Zona 3 • Madrid</p>
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-800 text-slate-900">135.000€</span>
                                <span class="text-sky-500 font-bold">Ver más <i class="fa-solid fa-arrow-right"></i></span>
                            </div>
                        </div>
                    </div>
                    <!-- Coche 2 -->
                    <div class="group cursor-pointer bg-slate-50 rounded-3xl overflow-hidden shadow-sm hover:shadow-xl transition"
                         onclick="openCar('Audi RS6 Avant', 'https://images.unsplash.com/photo-1606152421802-db97b9c7a11b?auto=format&fit=crop&q=80&w=800', '118.900€', '600 CV • 2023')">
                        <div class="h-64 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1606152421802-db97b9c7a11b?auto=format&fit=crop&q=80&w=800" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-bold">Audi RS6 Avant</h3>
                            <p class="text-slate-500 text-sm mb-4">Zona 2 • Barcelona</p>
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-800 text-slate-900">118.900€</span>
                                <span class="text-sky-500 font-bold">Ver más <i class="fa-solid fa-arrow-right"></i></span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- SUBPÁGINA: DETALLE DEL COCHE -->
    <div id="page-car" class="page-overlay">
        <div class="max-w-6xl mx-auto px-6 py-20">
            <button onclick="closePage('car')" class="mb-10 text-slate-900 font-bold flex items-center gap-2">
                <i class="fa-solid fa-arrow-left"></i> VOLVER AL STOCK
            </button>
            <div class="grid lg:grid-cols-2 gap-16">
                <div class="rounded-[2rem] overflow-hidden shadow-2xl h-[500px]">
                    <img id="car-img" src="" class="w-full h-full object-cover">
                </div>
                <div>
                    <h2 id="car-title" class="text-5xl font-800 text-slate-900 mb-4 font-montserrat"></h2>
                    <p id="car-spec" class="text-sky-500 font-bold text-xl mb-6"></p>
                    <div id="car-price" class="text-4xl font-800 text-slate-900 mb-8"></div>
                    <div class="bg-slate-50 p-8 rounded-3xl mb-8">
                        <h4 class="font-bold mb-4 uppercase text-xs text-slate-400 tracking-widest">Información Técnica</h4>
                        <ul class="space-y-3 text-slate-600">
                            <li><i class="fa-solid fa-check text-sky-500 mr-2"></i> Inspección técnica de 300 puntos</li>
                            <li><i class="fa-solid fa-check text-sky-500 mr-2"></i> Garantía Shiftly Gold (24 meses)</li>
                            <li><i class="fa-solid fa-check text-sky-500 mr-2"></i> Transferencia incluida</li>
                        </ul>
                    </div>
                    <button class="w-full bg-slate-900 text-white py-4 rounded-xl font-bold hover:bg-sky-500 transition">Reservar Vehículo</button>
                </div>
            </div>
        </div>
    </div>

    <!-- SUBPÁGINA: LOGIN -->
    <div id="page-login" class="page-overlay bg-slate-100 flex items-center justify-center">
        <div class="bg-white p-12 rounded-[2.5rem] shadow-2xl w-full max-w-md">
            <div class="text-center mb-10">
                <div class="bg-sky-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                    <i class="fa-solid fa-user-lock text-sky-600 text-2xl"></i>
                </div>
                <h2 class="text-2xl font-800 font-montserrat">Shiftly Inside</h2>
                <p class="text-slate-400">Acceso exclusivo para empleados</p>
            </div>
            <div class="space-y-5">
                <input type="email" id="user-email" value="comercial@shiftly.com" class="w-full px-5 py-4 bg-slate-50 rounded-xl border border-slate-200 focus:outline-sky-500">
                <input type="password" id="user-pass" value="motors2025" class="w-full px-5 py-4 bg-slate-50 rounded-xl border border-slate-200 focus:outline-sky-500">
                <button onclick="login()" class="w-full bg-slate-900 text-white py-4 rounded-xl font-bold hover:bg-sky-600 transition">ENTRAR</button>
                <button onclick="closePage('login')" class="w-full text-slate-400 text-sm pt-2">Cerrar</button>
            </div>
        </div>
    </div>

    <!-- SUBPÁGINA: DASHBOARD EMPLEADO (KPIs) -->
    <div id="page-dashboard" class="page-overlay portal-bg">
        <div class="max-w-7xl mx-auto px-6 py-12">
            <!-- Header Dashboard -->
            <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-6 mb-16 border-b border-white/10 pb-10">
                <div>
                    <h2 class="text-4xl font-800 font-montserrat">Mi Retribución Variable</h2>
                    <p class="text-sky-400">Panel de Control Comercial • Período Actual</p>
                </div>
                <div class="flex gap-4">
                    <div class="bg-white/5 px-6 py-3 rounded-2xl border border-white/10">
                        <span class="block text-[10px] text-slate-400 uppercase font-bold">Base Variable Anual</span>
                        <span class="text-xl font-bold">20.093,18€</span>
                    </div>
                    <button onclick="logout()" class="bg-red-500/10 hover:bg-red-500/20 text-red-500 px-6 py-3 rounded-2xl transition font-bold">SALIR</button>
                </div>
            </div>

            <div class="grid lg:grid-cols-3 gap-12">
                <!-- Columna: KPIs (Accionables) -->
                <div class="lg:col-span-2 space-y-6">
                    <h3 class="text-xl font-bold mb-6 font-montserrat">Selecciona KPIs cumplidos:</h3>
                    
                    <div class="kpi-card p-6 flex items-center justify-between" onclick="toggleKPI(0)">
                        <div class="flex items-center gap-4">
                            <div class="check-circle" id="check-0"><i class="fa-solid fa-check text-white text-xs"></i></div>
                            <div>
                                <h4 class="font-bold text-lg">Unidades de Venta</h4>
                                <p class="text-sm text-slate-400">Meta: 5u / mes</p>
                            </div>
                        </div>
                        <div class="text-right"><span class="text-sky-400 font-bold">Cumplido</span></div>
                    </div>

                    <div class="kpi-card p-6 flex items-center justify-between" onclick="toggleKPI(1)">
                        <div class="flex items-center gap-4">
                            <div class="check-circle" id="check-1"><i class="fa-solid fa-check text-white text-xs"></i></div>
                            <div>
                                <h4 class="font-bold text-lg">Margen Bruto de Operación</h4>
                                <p class="text-sm text-slate-400">Meta: 10% por operación</p>
                            </div>
                        </div>
                        <div class="text-right"><span class="text-sky-400 font-bold">Cumplido</span></div>
                    </div>

                    <div class="kpi-card p-6 flex items-center justify-between" onclick="toggleKPI(2)">
                        <div class="flex items-center gap-4">
                            <div class="check-circle" id="check-2"><i class="fa-solid fa-check text-white text-xs"></i></div>
                            <div>
                                <h4 class="font-bold text-lg">Penetración de Financiación</h4>
                                <p class="text-sm text-slate-400">Meta: 45% de las ventas</p>
                            </div>
                        </div>
                        <div class="text-right"><span class="text-sky-400 font-bold">Cumplido</span></div>
                    </div>

                    <div class="kpi-card p-6 flex items-center justify-between" onclick="toggleKPI(3)">
                        <div class="flex items-center gap-4">
                            <div class="check-circle" id="check-3"><i class="fa-solid fa-check text-white text-xs"></i></div>
                            <div>
                                <h4 class="font-bold text-lg">Satisfacción del Cliente</h4>
                                <p class="text-sm text-slate-400">Meta: NPS > 80 puntos</p>
                            </div>
                        </div>
                        <div class="text-right"><span class="text-sky-400 font-bold">Cumplido</span></div>
                    </div>

                    <div class="kpi-card p-6 flex items-center justify-between" onclick="toggleKPI(4)">
                        <div class="flex items-center gap-4">
                            <div class="check-circle" id="check-4"><i class="fa-solid fa-check text-white text-xs"></i></div>
                            <div>
                                <h4 class="font-bold text-lg">Uso del CRM</h4>
                                <p class="text-sm text-slate-400">Meta: 100% registros</p>
                            </div>
                        </div>
                        <div class="text-right"><span class="text-sky-400 font-bold">Cumplido</span></div>
                    </div>
                </div>

                <!-- Columna: Resultado Retribución -->
                <div class="lg:col-span-1">
                    <div class="bg-white rounded-[2.5rem] p-10 text-slate-900 sticky top-28 shadow-2xl">
                        <h3 class="font-bold text-2xl mb-8 font-montserrat">Resultado Final</h3>
                        
                        <div class="space-y-6 mb-10">
                            <div class="flex justify-between items-center pb-4 border-b">
                                <span class="text-slate-500">KPIs conseguidos:</span>
                                <span class="font-bold text-xl" id="res-count">0 / 5</span>
                            </div>
                            <div class="flex justify-between items-center pb-4 border-b">
                                <span class="text-slate-500">% de Retribución:</span>
                                <span class="font-bold text-xl text-sky-600" id="res-percent">0%</span>
                            </div>
                        </div>

                        <div class="bg-slate-900 rounded-3xl p-8 text-white text-center">
                            <span class="block text-xs uppercase text-slate-400 mb-2 font-bold tracking-widest">Total Variable a Cobrar</span>
                            <div class="text-4xl font-900" id="res-total">0,00€</div>
                        </div>

                        <p class="text-[10px] text-slate-400 mt-6 text-center italic">
                            *Cálculo basado en política retributiva interna Shiftly Motors 2025.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Navegación entre páginas
        function openPage(id) {
            document.getElementById('page-' + id).classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closePage(id) {
            document.getElementById('page-' + id).classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Abrir Detalle de Coche
        function openCar(title, img, price, spec) {
            document.getElementById('car-title').innerText = title;
            document.getElementById('car-img').src = img;
            document.getElementById('car-price').innerText = price;
            document.getElementById('car-spec').innerText = spec;
            openPage('car');
        }

        // Login
        function login() {
            const email = document.getElementById('user-email').value;
            const pass = document.getElementById('user-pass').value;
            if(email === 'comercial@shiftly.com' && pass === 'motors2025') {
                closePage('login');
                openPage('dashboard');
            } else {
                alert("Credenciales incorrectas (comercial@shiftly.com / motors2025)");
            }
        }

        function logout() {
            closePage('dashboard');
        }

        // LÓGICA DE RETRIBUCIÓN DINÁMICA
        const BASE_VARIABLE = 20093.18;
        let kpisSelected = [false, false, false, false, false];

        function toggleKPI(index) {
            kpisSelected[index] = !kpisSelected[index];
            updateDashboard();
        }

        function updateDashboard() {
            const count = kpisSelected.filter(v => v).length;
            let percentage = 0;

            // Escala definida en el prompt
            if(count === 1) percentage = 0.05;
            else if(count === 2) percentage = 0.15;
            else if(count === 3) percentage = 0.30;
            else if(count === 4) percentage = 0.50;
            else if(count === 5) percentage = 1.00;

            const total = BASE_VARIABLE * percentage;

            // UI Actualización
            kpisSelected.forEach((selected, i) => {
                const card = document.querySelectorAll('.kpi-card')[i];
                const check = document.getElementById('check-' + i);
                if(selected) {
                    card.classList.add('selected');
                } else {
                    card.classList.remove('selected');
                }
            });

            document.getElementById('res-count').innerText = `${count} / 5`;
            document.getElementById('res-percent').innerText = `${(percentage * 100).toFixed(0)}%`;
            document.getElementById('res-total').innerText = total.toLocaleString('es-ES', { minimumFractionDigits: 2, maximumFractionDigits: 2 }) + '€';
        }
    </script>
</body>
</html>

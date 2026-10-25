# profremservice[elite_renovation_landing_page.html](https://github.com/user-attachments/files/33914574/elite_renovation_landing_page.html)
<!DOCTYPE html>
<html lang="ru" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Renovation — Премиальный ремонт под ключ & CRM</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            dark: '#0a0d0e',
                            surface: '#111618',
                            card: '#161c1f',
                            accent: '#D4AF37', // Premium Gold Accent
                            accentHover: '#C5A059',
                            goldLight: '#F3E5AB',
                            grayText: '#9CA3AF'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <!-- SheetJS для экспорта в Excel -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0a0d0e;
            color: #f3f4f6;
            overflow-x: hidden;
        }

        /* Glassmorphism Styles */
        .glass-nav {
            background: rgba(10, 13, 14, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(212, 175, 55, 0.15);
        }

        .glass-card {
            background: rgba(22, 28, 31, 0.7);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.07);
        }

        .glass-card:hover {
            border-color: rgba(212, 175, 55, 0.35);
        }

        .gold-gradient-text {
            background: linear-gradient(135deg, #FFF 10%, #F3E5AB 50%, #D4AF37 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Custom Range Slider */
        input[type=range] {
            -webkit-appearance: none;
            background: #1f282c;
            border-radius: 8px;
            height: 8px;
        }

        input[type=range]::-webkit-slider-thumb {
            -webkit-appearance: none;
            height: 24px;
            width: 24px;
            border-radius: 50%;
            background: #D4AF37;
            cursor: pointer;
            box-shadow: 0 0 12px rgba(212, 175, 55, 0.6);
            transition: transform 0.15s ease;
        }

        input[type=range]::-webkit-slider-thumb:hover {
            transform: scale(1.15);
        }

        /* Interactive Before/After Comparison Slider */
        .ba-container {
            position: relative;
            overflow: hidden;
            border-radius: 1rem;
            user-select: none;
            touch-action: pan-y;
        }

        .ba-img-after {
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 50%;
            overflow: hidden;
            border-right: 3px solid #D4AF37;
        }

        .ba-slider-line {
            position: absolute;
            z-index: 20;
            top: 0;
            bottom: 0;
            left: 50%;
            width: 3px;
            background: #D4AF37;
            cursor: ew-resize;
            transform: translateX(-50%);
        }

        .ba-handle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: #D4AF37;
            color: #0a0d0e;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.6);
        }

        .active-calc-option {
            border-color: #D4AF37 !important;
            background: rgba(212, 175, 55, 0.12) !important;
            box-shadow: 0 0 15px rgba(212, 175, 55, 0.15);
        }
    </style>
</head>
<body class="antialiased selection:bg-brand-accent selection:text-black">

    <!-- HEADER NAVIGATION -->
    <header class="fixed top-0 left-0 w-full z-50 glass-nav transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Logo -->
                <a href="#" class="flex items-center gap-3 group">
                    <div class="w-11 h-11 rounded-xl bg-gradient-to-br from-brand-accent via-amber-500 to-amber-700 flex items-center justify-center text-black font-extrabold text-xl shadow-lg shadow-amber-500/20 group-hover:scale-105 transition-transform">
                        <i class="fa-solid fa-crown"></i>
                    </div>
                    <div>
                        <span class="text-xl sm:text-2xl font-black tracking-wider gold-gradient-text">ELITE</span>
                        <span class="block text-[10px] tracking-[0.25em] text-brand-accent uppercase -mt-1 font-bold">Renovation</span>
                    </div>
                </a>

                <!-- Desktop Nav Links -->
                <nav class="hidden lg:flex items-center space-x-8 font-medium text-sm text-gray-300">
                    <a href="#services" class="hover:text-brand-accent transition-colors">Услуги</a>
                    <a href="#calculator" class="hover:text-brand-accent transition-colors">Калькулятор</a>
                    <a href="#portfolio" class="hover:text-brand-accent transition-colors">Портфолио</a>
                    <a href="#reviews" class="hover:text-brand-accent transition-colors">Отзывы</a>
                </nav>

                <!-- Phone & CRM Button -->
                <div class="hidden sm:flex items-center space-x-5">
                    <a href="tel:+74959998877" class="text-right">
                        <div class="text-sm font-extrabold text-white hover:text-brand-accent transition-colors">+7 (495) 999-88-77</div>
                        <div class="text-[10px] text-emerald-400 flex items-center justify-end gap-1 font-medium">
                            <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span> Работаем ежедневно
                        </div>
                    </a>

                    <!-- Кнопка открытия CRM -->
                    <button onclick="toggleCRM()" class="bg-slate-800 hover:bg-slate-700 text-brand-accent border border-brand-accent/40 font-bold px-3.5 py-2.5 rounded-xl transition-all hover:scale-105 active:scale-95 text-xs flex items-center gap-2" title="Панель заявок">
                        <i class="fa-solid fa-chart-line text-sm"></i>
                        <span>CRM</span>
                    </button>

                    <button onclick="openModal('Заказать обратный звонок')" class="bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-bold px-5 py-2.5 rounded-xl shadow-lg shadow-amber-500/20 transition-all hover:scale-105 active:scale-95 text-xs uppercase tracking-wider">
                        Заказать звонок
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <div class="lg:hidden flex items-center gap-3">
                    <button onclick="toggleCRM()" class="bg-slate-800 text-brand-accent p-2 rounded-lg border border-brand-accent/30 text-xs">
                        <i class="fa-solid fa-chart-line text-base"></i>
                    </button>
                    <button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="text-gray-300 hover:text-white p-2">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden lg:hidden bg-brand-dark/95 backdrop-blur-xl border-b border-gray-800 px-6 pt-4 pb-6 space-y-3">
            <a href="#services" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Услуги</a>
            <a href="#calculator" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Калькулятор</a>
            <div class="pt-4 border-t border-gray-800 space-y-2">
                <button onclick="toggleCRM(); toggleMobileMenu();" class="w-full bg-slate-800 text-brand-accent border border-brand-accent/40 font-bold py-3 rounded-xl uppercase text-xs tracking-wider flex items-center justify-center gap-2">
                    <i class="fa-solid fa-chart-line"></i> Панель заявок (CRM)
                </button>
                <button onclick="openModal('Заказать быстрый звонок'); toggleMobileMenu();" class="w-full bg-brand-accent text-black font-bold py-3 rounded-xl uppercase text-xs tracking-wider">
                    Заказать звонок
                </button>
            </div>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="relative pt-32 pb-20 md:pt-44 md:pb-32 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                
                <div class="lg:col-span-7 space-y-8 text-center lg:text-left">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-brand-card/90 border border-brand-accent/30 text-brand-accent text-xs font-semibold tracking-wide">
                        <i class="fa-solid fa-award"></i> Гарантия 5 лет по официальному договору
                    </div>

                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-black tracking-tight text-white leading-tight">
                        Безупречный ремонт <br class="hidden sm:inline">
                        <span class="gold-gradient-text">квартир и домов под ключ</span>
                    </h1>

                    <p class="text-gray-300 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 font-light leading-relaxed">
                        Реализуем интерьерные решения любой сложности. Расчёт точной сметы за 1 минуту, фиксированная цена без скрытых переплат.
                    </p>

                    <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start pt-2">
                        <a href="#calculator" class="bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-bold px-8 py-4 rounded-xl shadow-xl shadow-amber-500/20 flex items-center justify-center gap-3 transition-all hover:scale-105 text-sm uppercase tracking-wider">
                            <i class="fa-solid fa-calculator text-base"></i>
                            Рассчитать стоимость
                        </a>
                    </div>
                </div>

                <!-- Before / After Slider -->
                <div class="lg:col-span-5">
                    <div class="glass-card p-4 rounded-2xl shadow-2xl relative">
                        <div class="ba-container h-80 sm:h-96 w-full cursor-ew-resize">
                            <img src="https://images.unsplash.com/photo-1581858726788-75bc0f6a952d?auto=format&fit=crop&w=1000&q=80" alt="До" class="absolute inset-0 w-full h-full object-cover">
                            <div class="ba-img-after">
                                <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=1000&q=80" alt="После" class="absolute top-0 left-0 max-w-none h-full object-cover">
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- CALCULATOR SECTION -->
    <section id="calculator" class="py-20 relative bg-brand-surface/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Калькулятор</h2>
                <p class="text-3xl font-extrabold text-white">Рассчитайте стоимость ремонта</p>
            </div>

            <div class="grid lg:grid-cols-12 gap-8 items-start">
                <div class="lg:col-span-8 glass-card p-6 rounded-2xl space-y-6">
                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-3">Площадь помещения: <span id="area-val" class="text-brand-accent font-black">75</span> м²</label>
                        <input type="range" id="area-range" min="20" max="300" value="75" oninput="updateCalculator()" class="w-full">
                    </div>
                </div>

                <div class="lg:col-span-4 glass-card p-6 rounded-2xl border-brand-accent/40 space-y-4">
                    <span class="text-xs text-gray-400 block uppercase">Предварительный расчёт:</span>
                    <div id="total-price" class="text-3xl font-black gold-gradient-text my-2">1 650 000 ₽</div>
                    <button onclick="submitCalculatorLead()" class="w-full bg-brand-accent text-black font-extrabold py-3.5 rounded-xl uppercase tracking-wider text-xs">
                        Отправить расчёт в CRM
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- CRM PANEL OVERLAY -->
    <section id="crm-panel" class="hidden fixed inset-0 z-50 bg-slate-950/95 backdrop-blur-xl overflow-y-auto text-slate-100 p-6">
        <div class="max-w-7xl mx-auto">
            <div class="flex items-center justify-between pb-6 border-b border-slate-800 mb-6">
                <div class="flex items-center space-x-3">
                    <div class="bg-brand-accent text-black p-2 rounded-xl font-bold">
                        <i class="fa-solid fa-chart-line text-lg"></i>
                    </div>
                    <h2 class="text-xl font-bold">Панель управления заявками (CRM)</h2>
                </div>
                <button onclick="toggleCRM()" class="p-2 bg-rose-600/20 text-rose-400 rounded-xl">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>

            <div class="bg-slate-900 rounded-2xl border border-slate-800 overflow-hidden">
                <table class="w-full text-left text-xs">
                    <thead class="bg-slate-950 text-slate-400 border-b border-slate-800">
                        <tr>
                            <th class="py-3 px-4">Клиент</th>
                            <th class="py-3 px-4">Телефон</th>
                            <th class="py-3 px-4">Услуга / Запрос</th>
                            <th class="py-3 px-4">Дата</th>
                            <th class="py-3 px-4 text-right">Действия</th>
                        </tr>
                    </thead>
                    <tbody id="leadsTableBody" class="divide-y divide-slate-800">
                        <!-- Leads go here -->
                    </tbody>
                </table>
            </div>
        </div>
    </section>

    <!-- MODAL FORM -->
    <div id="modalForm" class="fixed inset-0 z-50 bg-black/80 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-brand-card rounded-2xl border border-brand-accent/30 max-w-md w-full p-6 relative">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <h3 id="modalFormTitle" class="text-lg font-bold text-white mb-4">Заказать звонок</h3>
            <form onsubmit="handleWebsiteSubmit(event)" class="space-y-4">
                <input type="hidden" id="formSubject" value="Заявка с сайта">
                <input type="text" id="custName" required placeholder="Ваше имя" class="w-full px-4 py-2 bg-brand-dark border border-gray-800 rounded-xl text-sm text-white">
                <input type="tel" id="custPhone" required placeholder="Ваш телефон" class="w-full px-4 py-2 bg-brand-dark border border-gray-800 rounded-xl text-sm text-white">
                <button type="submit" class="w-full bg-brand-accent text-black font-extrabold py-3 rounded-xl uppercase tracking-wider text-xs">
                    Отправить
                </button>
            </form>
        </div>
    </div>

    <!-- SCRIPTS -->
    <script>
        let leads = JSON.parse(localStorage.getItem('crm_leads')) || [
            { id: 1, name: 'Михаил Решетов', phone: '+7 (926) 111-22-33', service: 'Капитальный ремонт', date: '2026-06-06 12:40' }
        ];

        function openModal(subject = 'Заявка с сайта') {
            document.getElementById('formSubject').value = subject;
            document.getElementById('modalFormTitle').innerText = subject;
            document.getElementById('modalForm').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('modalForm').classList.add('hidden');
        }

        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        function toggleCRM() {
            const panel = document.getElementById('crm-panel');
            panel.classList.toggle('hidden');
            if (!panel.classList.contains('hidden')) renderLeads();
        }

        function handleWebsiteSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('custName').value;
            const phone = document.getElementById('custPhone').value;
            const subject = document.getElementById('formSubject').value;

            addLeadToCRM(name, phone, subject);
            closeModal();
            alert('Спасибо! Ваша заявка передана в CRM.');
            e.target.reset();
        }

        function updateCalculator() {
            const area = document.getElementById('area-range').value;
            document.getElementById('area-val').innerText = area;
            const total = Math.round(area * 22000);
            document.getElementById('total-price').innerText = total.toLocaleString('ru-RU') + ' ₽';
        }

        function submitCalculatorLead() {
            const area = document.getElementById('area-range').value;
            const price = document.getElementById('total-price').innerText;
            const phone = prompt('Укажите ваш телефон:');
            if (phone) {
                addLeadToCRM('Клиент с калькулятора', phone, 'Расчёт сметы: ' + price);
                alert('Смета сохранена в CRM!');
            }
        }

        function addLeadToCRM(name, phone, service) {
            const now = new Date();
            const dateStr = now.toISOString().slice(0,10) + ' ' + now.toTimeString().slice(0,5);
            leads.unshift({ id: Date.now(), name, phone, service, date: dateStr });
            localStorage.setItem('crm_leads', JSON.stringify(leads));
            renderLeads();
        }

        function renderLeads() {
            const tbody = document.getElementById('leadsTableBody');
            if (!tbody) return;
            tbody.innerHTML = '';
            leads.forEach(lead => {
                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td class="py-3 px-4 font-medium text-white">${lead.name}</td>
                    <td class="py-3 px-4 text-slate-300 font-mono">${lead.phone}</td>
                    <td class="py-3 px-4 text-slate-400">${lead.service}</td>
                    <td class="py-3 px-4 text-slate-500">${lead.date}</td>
                    <td class="py-3 px-4 text-right">
                        <button onclick="deleteLead(${lead.id})" class="text-rose-400"><i class="fa-solid fa-trash"></i></button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        function deleteLead(id) {
            leads = leads.filter(l => l.id !== id);
            localStorage.setItem('crm_leads', JSON.stringify(leads));
            renderLeads();
        }
    </script>
</body>
</html>

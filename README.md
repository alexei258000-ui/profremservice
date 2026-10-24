# profremservice[elite_renovation_landing_page.html](https://github.com/user-attachments/files/33914574/elite_renovation_landing_page.html)
<!DOCTYPE html>
<html lang="ru" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Renovation — Премиальный ремонт квартир и домов под ключ в Москве</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
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

        /* Custom Gold Glow Gradient */
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

    <!-- 1. HEADER NAVIGATION -->
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
                    <a href="#process" class="hover:text-brand-accent transition-colors">Этапы</a>
                    <a href="#reviews" class="hover:text-brand-accent transition-colors">Отзывы</a>
                    <a href="#faq" class="hover:text-brand-accent transition-colors">FAQ</a>
                    <a href="#contact" class="hover:text-brand-accent transition-colors">Контакты</a>
                </nav>

                <!-- Phone & CTA -->
                <div class="hidden sm:flex items-center space-x-5">
                    <a href="tel:+74959998877" class="text-right">
                        <div class="text-sm font-extrabold text-white hover:text-brand-accent transition-colors">+7 (495) 999-88-77</div>
                        <div class="text-[10px] text-emerald-400 flex items-center justify-end gap-1 font-medium">
                            <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span> Работаем ежедневно
                        </div>
                    </a>
                    <button onclick="openModal('Заказать обратный звонок')" class="bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-bold px-5 py-2.5 rounded-xl shadow-lg shadow-amber-500/20 transition-all hover:scale-105 active:scale-95 text-xs uppercase tracking-wider">
                        Заказать звонок
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <div class="lg:hidden flex items-center">
                    <button id="mobile-menu-btn" class="text-gray-300 hover:text-white p-2">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden lg:hidden bg-brand-dark/95 backdrop-blur-xl border-b border-gray-800 px-6 pt-4 pb-6 space-y-3">
            <a href="#services" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Услуги</a>
            <a href="#calculator" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Калькулятор</a>
            <a href="#portfolio" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Портфолио</a>
            <a href="#process" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Этапы работ</a>
            <a href="#reviews" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Отзывы</a>
            <a href="#faq" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Частые вопросы</a>
            <a href="#contact" class="block text-gray-300 hover:text-brand-accent py-2">Контакты</a>
            <div class="pt-4 border-t border-gray-800">
                <button onclick="openModal('Заказать быстрый звонок')" class="w-full bg-brand-accent text-black font-bold py-3 rounded-xl uppercase text-xs tracking-wider">
                    Заказать звонок
                </button>
            </div>
        </div>
    </header>

    <!-- 2. HERO SECTION -->
    <section class="relative pt-32 pb-20 md:pt-44 md:pb-32 overflow-hidden">
        <!-- Ambient Glowing Orbs -->
        <div class="absolute top-1/4 left-10 w-96 h-96 bg-amber-600/10 rounded-full filter blur-[140px] pointer-events-none"></div>
        <div class="absolute top-1/3 right-10 w-96 h-96 bg-brand-accent/10 rounded-full filter blur-[160px] pointer-events-none"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                
                <!-- Left Column (Text & CTAs) -->
                <div class="lg:col-span-7 space-y-8 text-center lg:text-left">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-brand-card/90 border border-brand-accent/30 text-brand-accent text-xs font-semibold tracking-wide">
                        <i class="fa-solid fa-award"></i> Гарантия 5 лет по официальному договору
                    </div>

                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-black tracking-tight text-white leading-tight">
                        Безупречный ремонт <br class="hidden sm:inline">
                        <span class="gold-gradient-text">квартир и домов под ключ</span>
                    </h1>

                    <p class="text-gray-300 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 font-light leading-relaxed">
                        Реализуем интерьерные решения любой сложности. Расчёт точной сметы за 1 минуту, фиксированная цена без скрытых переплат и закупка материалов по оптовым ценам.
                    </p>

                    <!-- CTA Buttons -->
                    <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start pt-2">
                        <a href="#calculator" class="bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-bold px-8 py-4 rounded-xl shadow-xl shadow-amber-500/20 flex items-center justify-center gap-3 transition-all hover:scale-105 active:scale-95 text-sm uppercase tracking-wider">
                            <i class="fa-solid fa-calculator text-base"></i>
                            Рассчитать стоимость
                        </a>
                        <a href="#portfolio" class="border border-gray-700 hover:border-brand-accent text-white hover:text-brand-accent font-semibold px-8 py-4 rounded-xl backdrop-blur-sm flex items-center justify-center gap-3 transition-all text-sm uppercase tracking-wider">
                            <i class="fa-solid fa-images text-base"></i>
                            Смотреть работы
                        </a>
                    </div>

                    <!-- Advantages Badges -->
                    <div class="pt-8 grid grid-cols-3 gap-4 border-t border-gray-800/80">
                        <div>
                            <div class="text-2xl sm:text-3xl font-extrabold text-white">10+ лет</div>
                            <div class="text-xs text-gray-400 mt-1">Опыта в премиум-сегменте</div>
                        </div>
                        <div>
                            <div class="text-2xl sm:text-3xl font-extrabold text-white">350+</div>
                            <div class="text-xs text-gray-400 mt-1">Сданных объектов</div>
                        </div>
                        <div>
                            <div class="text-2xl sm:text-3xl font-extrabold text-white">100%</div>
                            <div class="text-xs text-gray-400 mt-1">Сдача точно в срок</div>
                        </div>
                    </div>
                </div>

                <!-- Right Column (Interactive Before/After Slider) -->
                <div class="lg:col-span-5">
                    <div class="glass-card p-4 rounded-2xl shadow-2xl relative">
                        <div class="flex items-center justify-between mb-3 px-2">
                            <span class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Результат работы</span>
                            <span class="text-[11px] px-2.5 py-1 rounded-full bg-brand-accent/20 text-brand-accent border border-brand-accent/30 font-medium">Потяните ползунок</span>
                        </div>
                        
                        <!-- BEFORE / AFTER INTERACTIVE SLIDER -->
                        <div class="ba-container h-80 sm:h-96 w-full cursor-ew-resize" id="hero-ba-slider">
                            <!-- BEFORE Image -->
                            <img src="https://images.unsplash.com/photo-1581858726788-75bc0f6a952d?auto=format&fit=crop&w=1000&q=80" alt="До ремонта" class="absolute inset-0 w-full h-full object-cover">
                            <span class="absolute top-4 right-4 bg-black/80 text-white text-xs px-3 py-1 rounded-full backdrop-blur-md font-bold">ДО</span>

                            <!-- AFTER Image Container -->
                            <div class="ba-img-after" id="ba-after-layer">
                                <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=1000&q=80" alt="После ремонта" class="absolute top-0 left-0 max-w-none h-full object-cover" id="ba-after-img">
                                <span class="absolute top-4 left-4 bg-brand-accent text-black font-extrabold text-xs px-3 py-1 rounded-full shadow-lg">ПОСЛЕ</span>
                            </div>

                            <!-- Slider Line & Handle -->
                            <div class="ba-slider-line" id="ba-handle-line">
                                <div class="ba-handle">
                                    <i class="fa-solid fa-left-right text-xs"></i>
                                </div>
                            </div>
                        </div>

                        <div class="mt-4 p-3 bg-brand-dark/60 rounded-xl flex items-center justify-between text-xs text-gray-300 border border-gray-800">
                            <div class="flex items-center gap-2">
                                <i class="fa-solid fa-location-dot text-brand-accent"></i> ЖК «Пресня Сити», 94 м²
                            </div>
                            <span class="text-brand-accent font-semibold">Дизайнерский ремонт</span>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 3. SERVICES SECTION -->
    <section id="services" class="py-20 bg-brand-surface/60 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Наши направления</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Виды ремонта и отделки</p>
                <p class="text-gray-400 mt-3 text-sm">Подбираем индивидуальный пакет услуг под ваши задачи и бюджет</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                
                <!-- Service 1 -->
                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between hover:-translate-y-1 transition-transform duration-300">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-paint-roller"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Косметический</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Быстрое обновление интерьера: выравнивание и покраска стен, замена напольных покрытий, сантехники и электрики.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 12 000 ₽/м²</div>
                        <button onclick="openModal('Консультация по Косметическому ремонту')" class="w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <!-- Service 2 -->
                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between hover:-translate-y-1 transition-transform duration-300 relative border-brand-accent/40">
                    <span class="absolute -top-3 right-4 bg-brand-accent text-black font-extrabold text-[10px] uppercase tracking-wider px-3 py-1 rounded-full">Популярный</span>
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/20 border border-brand-accent text-brand-accent flex items-center justify-center font-bold text-xl mb-6 shadow-md shadow-brand-accent/20">
                            <i class="fa-solid fa-hammer"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Капитальный</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Полная замена всех инженерных сетей, штукатурка по маякам, стяжка пола, выравнивание углов под 90° и финишная отделка.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 22 000 ₽/м²</div>
                        <button onclick="openModal('Консультация по Капитальному ремонту')" class="w-full py-2.5 bg-brand-accent hover:bg-brand-accentHover text-xs font-bold text-black rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <!-- Service 3 -->
                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between hover:-translate-y-1 transition-transform duration-300">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-compass-drafting"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Дизайнерский</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Ремонт по уникальному 3D-проекту с авторским надзором, сложным световым сценарием и премиальными материалами.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 35 000 ₽/м²</div>
                        <button onclick="openModal('Консультация по Дизайнерскому ремонту')" class="w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <!-- Service 4 -->
                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between hover:-translate-y-1 transition-transform duration-300">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-house-chimney-window"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Ремонт домов</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Комплексная отделка коттеджей и таунхаусов: фасадные работы, монтаж котельных, отопления и системы «Умный дом».</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 28 000 ₽/м²</div>
                        <button onclick="openModal('Консультация по Ремонту домов')" class="w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 4. CALCULATOR SECTION -->
    <section id="calculator" class="py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Онлайн калькулятор</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Рассчитайте стоимость сметы</p>
                <p class="text-gray-400 mt-3 text-sm">Укажите параметры вашего объекта и получите мгновенный расчёт бюджета</p>
            </div>

            <div class="grid lg:grid-cols-12 gap-8 items-start">
                
                <!-- Calculator Inputs -->
                <div class="lg:col-span-8 glass-card p-6 sm:p-8 rounded-2xl space-y-8">
                    
                    <!-- Step 1: Property Type -->
                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-4">1. Тип недвижимости</label>
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                            <button type="button" class="calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all active-calc-option" data-housing="1">
                                <i class="fa-solid fa-building text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Новостройка</div>
                                <div class="text-xs text-gray-400 mt-1">Черновая отделка / бетон</div>
                            </button>
                            <button type="button" class="calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-housing="1.15">
                                <i class="fa-solid fa-house-chimney text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Вторичка</div>
                                <div class="text-xs text-gray-400 mt-1">С демонтажем отделки</div>
                            </button>
                            <button type="button" class="calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-housing="1.25">
                                <i class="fa-solid fa-house text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Коттедж / Дом</div>
                                <div class="text-xs text-gray-400 mt-1">Инженерные коммуникации</div>
                            </button>
                        </div>
                    </div>

                    <!-- Step 2: Repair Class -->
                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-4">2. Класс ремонта</label>
                        <div class="grid grid-cols-1 sm:grid-cols-4 gap-3">
                            <button type="button" class="calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="12000">
                                <div class="font-bold text-white text-xs">Косметический</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">12 000 ₽/м²</div>
                            </button>
                            <button type="button" class="calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all active-calc-option" data-price="22000">
                                <div class="font-bold text-white text-xs">Капитальный</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">22 000 ₽/м²</div>
                            </button>
                            <button type="button" class="calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="35000">
                                <div class="font-bold text-white text-xs">Дизайнерский</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">35 000 ₽/м²</div>
                            </button>
                            <button type="button" class="calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="50000">
                                <div class="font-bold text-white text-xs">Премиум / Авторский</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">50 000 ₽/м²</div>
                            </button>
                        </div>
                    </div>

                    <!-- Step 3: Area Range -->
                    <div>
                        <div class="flex justify-between items-center mb-3">
                            <label class="text-sm font-bold text-gray-200">3. Площадь помещения</label>
                            <span class="text-2xl font-black text-brand-accent"><span id="area-val">75</span> м²</span>
                        </div>
                        <input type="range" id="area-range" min="20" max="300" value="75" class="w-full cursor-pointer">
                        <div class="flex justify-between text-xs text-gray-500 mt-2">
                            <span>20 м²</span>
                            <span>150 м²</span>
                            <span>300 м²</span>
                        </div>
                    </div>

                    <!-- Step 4: Additional Options -->
                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-4">4. Дополнительные опции</label>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                            <label class="flex items-center gap-3 p-3 rounded-xl border border-gray-800 bg-brand-dark/40 cursor-pointer hover:border-gray-700 transition">
                                <input type="checkbox" class="calc-addon rounded text-brand-accent focus:ring-0 bg-gray-800 border-gray-700" data-addon="2500" checked>
                                <span class="text-xs text-gray-300">Дизайн-проект (+2 500 ₽/м²)</span>
                            </label>
                            <label class="flex items-center gap-3 p-3 rounded-xl border border-gray-800 bg-brand-dark/40 cursor-pointer hover:border-gray-700 transition">
                                <input type="checkbox" class="calc-addon rounded text-brand-accent focus:ring-0 bg-gray-800 border-gray-700" data-addon="1500" checked>
                                <span class="text-xs text-gray-300">Закупка & доставка материалов (+1 500 ₽/м²)</span>
                            </label>
                            <label class="flex items-center gap-3 p-3 rounded-xl border border-gray-800 bg-brand-dark/40 cursor-pointer hover:border-gray-700 transition">
                                <input type="checkbox" class="calc-addon rounded text-brand-accent focus:ring-0 bg-gray-800 border-gray-700" data-addon="1000">
                                <span class="text-xs text-gray-300">Демонтажные работы (+1 000 ₽/м²)</span>
                            </label>
                            <label class="flex items-center gap-3 p-3 rounded-xl border border-gray-800 bg-brand-dark/40 cursor-pointer hover:border-gray-700 transition">
                                <input type="checkbox" class="calc-addon rounded text-brand-accent focus:ring-0 bg-gray-800 border-gray-700" data-addon="500" checked>
                                <span class="text-xs text-gray-300">Клининг после ремонта (+500 ₽/м²)</span>
                            </label>
                        </div>
                    </div>

                </div>

                <!-- Calculator Output Card -->
                <div class="lg:col-span-4 glass-card p-6 sm:p-8 rounded-2xl border-brand-accent/40 space-y-6 sticky top-28">
                    <h3 class="text-lg font-extrabold text-white border-b border-gray-800 pb-4">Предварительная смета</h3>

                    <div class="space-y-3 text-xs">
                        <div class="flex justify-between text-gray-400">
                            <span>Примерный срок:</span>
                            <span id="calc-days" class="text-white font-bold">50-65 дней</span>
                        </div>
                        <div class="flex justify-between text-gray-400">
                            <span>Черновые материалы:</span>
                            <span class="text-emerald-400 font-bold">Включены</span>
                        </div>
                        <div class="flex justify-between text-gray-400">
                            <span>Технадзор и контроль:</span>
                            <span class="text-emerald-400 font-bold">Бесплатно</span>
                        </div>
                        <div class="flex justify-between text-gray-400">
                            <span>Гарантийный срок:</span>
                            <span class="text-brand-accent font-bold">5 лет</span>
                        </div>
                    </div>

                    <div class="pt-4 border-t border-gray-800">
                        <span class="text-xs text-gray-400 block uppercase font-semibold">Итоговая стоимость:</span>
                        <div id="total-price" class="text-3xl sm:text-4xl font-black gold-gradient-text my-2">
                            1 950 000 ₽
                        </div>
                        <p class="text-[11px] text-gray-500">*Фиксируется в договоре после замера</p>
                    </div>

                    <button onclick="openModal('Зафиксировать скидку 10% по калькулятору')" class="w-full bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-extrabold py-4 rounded-xl shadow-xl shadow-amber-500/20 transition duration-200 text-xs uppercase tracking-wider">
                        Зафиксировать скидку 10%
                    </button>
                    
                    <p class="text-center text-xs text-gray-400 flex items-center justify-center gap-2">
                        <i class="fa-solid fa-shield-halved text-brand-accent"></i> Выезд замерщика бесплатно
                    </p>
                </div>

            </div>
        </div>
    </section>

    <!-- 5. PORTFOLIO GALLERY -->
    <section id="portfolio" class="py-20 bg-brand-surface/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-12">
                <div>
                    <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Портфолио</h2>
                    <p class="text-3xl sm:text-4xl font-extrabold text-white">Реализованные объекты</p>
                </div>

                <!-- Filter Tabs -->
                <div class="flex flex-wrap gap-2 mt-6 md:mt-0" id="portfolio-filters">
                    <button class="filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-brand-accent text-black transition-all" data-filter="all">Все</button>
                    <button class="filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-brand-card text-gray-300 hover:text-white border border-gray-800 transition-all" data-filter="living">Гостиная</button>
                    <button class="filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-brand-card text-gray-300 hover:text-white border border-gray-800 transition-all" data-filter="kitchen">Кухня</button>
                    <button class="filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-brand-card text-gray-300 hover:text-white border border-gray-800 transition-all" data-filter="bath">Ванная</button>
                    <button class="filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-brand-card text-gray-300 hover:text-white border border-gray-800 transition-all" data-filter="bedroom">Спальня</button>
                </div>
            </div>

            <!-- Portfolio Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" id="portfolio-grid">
                
                <!-- Card 1 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="living">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Современная гостиная">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=1200&q=80', 'Минималистичная гостиная в ЖК «Символ»')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Гостиная • 42 м²</span>
                            <span>Бюджет: 1.8 млн ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">ЖК «Символ», ул. Серпа и Молота</h3>
                        <p class="text-xs text-gray-400">Скрытые двери, теневой профиль и мультизонное LED-освещение.</p>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="kitchen">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1556911220-e15b29be8c8f?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Кухня">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1556911220-e15b29be8c8f?auto=format&fit=crop&w=1200&q=80', 'Кухня с островом')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Кухня • 28 м²</span>
                            <span>Бюджет: 1.2 млн ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">Кухня-столовая с островом</h3>
                        <p class="text-xs text-gray-400">Керамогранит крупного формата, встроенная техника, фартук из кварцита.</p>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="bath">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1584622650111-993a426fbf0a?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Ванная">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1584622650111-993a426fbf0a?auto=format&fit=crop&w=1200&q=80', 'Мастер-ванная')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Ванная • 14 м²</span>
                            <span>Бюджет: 850 тыс ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">Мастер-ванная в SPA стиле</h3>
                        <p class="text-xs text-gray-400">Встроенные термостаты, душевая трап-система и тёплые стены.</p>
                    </div>
                </div>

                <!-- Card 4 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="bedroom">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1616594039964-ae9021a400a0?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Спальня">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1616594039964-ae9021a400a0?auto=format&fit=crop&w=1200&q=80', 'Спальня с гардеробной')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Спальня • 24 м²</span>
                            <span>Бюджет: 950 тыс ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">Спальня с гардеробной зоной</h3>
                        <p class="text-xs text-gray-400">Акустическая шумоизоляция, мягкие стеновые панели и парящая кровать.</p>
                    </div>
                </div>

                <!-- Card 5 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="living">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Коттедж">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=1200&q=80', 'Загородный дом в Новогорске')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Дом • 210 м²</span>
                            <span>Бюджет: 5.4 млн ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">Коттедж в Новогорске</h3>
                        <p class="text-xs text-gray-400">Полный комплекс инженерных работ, панорамное остекление, каминная зона.</p>
                    </div>
                </div>

                <!-- Card 6 -->
                <div class="portfolio-item group glass-card rounded-2xl overflow-hidden" data-category="kitchen">
                    <div class="relative overflow-hidden h-64">
                        <img src="https://images.unsplash.com/photo-1507089947368-19c1da9775ae?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" alt="Кухня неоклассика">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition duration-300 flex items-end p-6">
                            <button onclick="openImageModal('https://images.unsplash.com/photo-1507089947368-19c1da9775ae?auto=format&fit=crop&w=1200&q=80', 'Кухня в неоклассике')" class="bg-brand-accent text-black font-bold text-xs px-4 py-2 rounded-lg">Увеличить фото</button>
                        </div>
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center text-xs text-brand-accent font-semibold">
                            <span>Кухня • 20 м²</span>
                            <span>Бюджет: 1.1 млн ₽</span>
                        </div>
                        <h3 class="text-lg font-bold text-white">Кухня в стиле неоклассика</h3>
                        <p class="text-xs text-gray-400">Фрезерованные фасады, латунная фурнитура и мраморные поверхности.</p>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 6. PROCESS SECTION (6 STEPS) -->
    <section id="process" class="py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Наш процесс</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">6 шагов к вашей идеальной квартире</p>
                <p class="text-gray-400 mt-3 text-sm">Прозрачный и понятный процесс работы на каждом этапе</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                
                <!-- Step 1 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">01</div>
                    <h3 class="text-lg font-bold text-white mb-2">Консультация и выезд</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Бесплатный выезд инженера-замерщика. Точные обмеры помещения лазерным сканером и консультация по планировке.</p>
                </div>

                <!-- Step 2 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">02</div>
                    <h3 class="text-lg font-bold text-white mb-2">Смета и договор</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Составление подробной сметы с фиксированной ценой. Подписание юридического договора с гарантией 5 лет.</p>
                </div>

                <!-- Step 3 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">03</div>
                    <h3 class="text-lg font-bold text-white mb-2">3D Дизайн-проект</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Разработка 3D-визуализации и полного пакета рабочих чертежей для строительной бригады (электрика, сантехника).</p>
                </div>

                <!-- Step 4 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">04</div>
                    <h3 class="text-lg font-bold text-white mb-2">Черновые работы</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Закупка чернових материалов со скидками. Демонтаж, возведение перегородок, разводка электрики и водоснабжения.</p>
                </div>

                <!-- Step 5 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">05</div>
                    <h3 class="text-lg font-bold text-white mb-2">Чистовая отделка</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Укладка плитки, паркета/ламината, поклейка обоев, монтаж освещения, дверей и сантехнических приборов.</p>
                </div>

                <!-- Step 6 -->
                <div class="glass-card p-6 rounded-2xl relative border-brand-accent/20">
                    <div class="w-10 h-10 rounded-xl bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm mb-4 shadow-md shadow-brand-accent/20">06</div>
                    <h3 class="text-lg font-bold text-white mb-2">Клининг и сдача</h3>
                    <p class="text-gray-400 text-xs leading-relaxed">Профессиональная генеральная уборка, вывоз мусора, подписание акта приёма-передачи и выдача гарантийного талона.</p>
                </div>

            </div>
        </div>
    </section>

    <!-- 7. REVIEWS SECTION -->
    <section id="reviews" class="py-20 bg-brand-surface/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Отзывы</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Что о нас говорят клиенты</p>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                
                <!-- Review 1 -->
                <div class="glass-card p-6 rounded-2xl space-y-4">
                    <div class="flex items-center gap-1 text-brand-accent">
                        <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-gray-300 text-xs leading-relaxed font-light">«Делали ремонт в новостройке 85 м². Очень понравилось, что смету не увеличили ни на рубль! Прораб постоянно присылал видеоотчеты в ТГ. Сдали даже на 5 дней раньше срока.»</p>
                    <div class="flex items-center gap-3 pt-2 border-t border-gray-800">
                        <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=150&q=80" class="w-10 h-10 rounded-full object-cover">
                        <div>
                            <div class="text-sm font-bold text-white">Екатерина М.</div>
                            <div class="text-[11px] text-gray-500">ЖК «Сердце Столицы»</div>
                        </div>
                    </div>
                </div>

                <!-- Review 2 -->
                <div class="glass-card p-6 rounded-2xl space-y-4">
                    <div class="flex items-center gap-1 text-brand-accent">
                        <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-gray-300 text-xs leading-relaxed font-light">«Обратился по рекомендации знакомых и не прогадал. Заказывал капитальный ремонт с дизайн-проектом. Качество выравнивания стен и укладки плитки — высший уровень!»</p>
                    <div class="flex items-center gap-3 pt-2 border-t border-gray-800">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=150&q=80" class="w-10 h-10 rounded-full object-cover">
                        <div>
                            <div class="text-sm font-bold text-white">Михаил Сергеев</div>
                            <div class="text-[11px] text-gray-500">Квартира 110 м²</div>
                        </div>
                    </div>
                </div>

                <!-- Review 3 -->
                <div class="glass-card p-6 rounded-2xl space-y-4">
                    <div class="flex items-center gap-1 text-brand-accent">
                        <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-gray-300 text-xs leading-relaxed font-light">«Большое спасибо команде Elite Renovation! Полностью взяли на себя закупку черновых материалов и шумные согласования с УК. Ремонт прошел без лишнего нерва.»</p>
                    <div class="flex items-center gap-3 pt-2 border-t border-gray-800">
                        <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=150&q=80" class="w-10 h-10 rounded-full object-cover">
                        <div>
                            <div class="text-sm font-bold text-white">Ольга и Андрей</div>
                            <div class="text-[11px] text-gray-500">Таунхаус в Новогорске</div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 8. FAQ ACCORDION SECTION -->
    <section id="faq" class="py-20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">FAQ</h2>
                <p class="text-3xl font-extrabold text-white">Часто задаваемые вопросы</p>
            </div>

            <div class="space-y-4">
                
                <!-- FAQ 1 -->
                <div class="glass-card rounded-xl overflow-hidden border border-gray-800">
                    <button class="faq-btn w-full p-5 text-left font-bold text-white flex justify-between items-center text-sm focus:outline-none">
                        <span>Как происходит оплата работ?</span>
                        <i class="fa-solid fa-chevron-down text-brand-accent transition-transform duration-300"></i>
                    </button>
                    <div class="faq-content hidden px-5 pb-5 text-xs text-gray-400 leading-relaxed border-t border-gray-800/50 pt-3">
                        Оплата происходит поэтапно. Мы разбиваем ремонт на 4–5 этапов. Вы оплачиваете каждый этап только после его выполнения, проверки техническим надзором и подписания промежуточного акта.
                    </div>
                </div>

                <!-- FAQ 2 -->
                <div class="glass-card rounded-xl overflow-hidden border border-gray-800">
                    <button class="faq-btn w-full p-5 text-left font-bold text-white flex justify-between items-center text-sm focus:outline-none">
                        <span>Фиксируется ли цена в договоре?</span>
                        <i class="fa-solid fa-chevron-down text-brand-accent transition-transform duration-300"></i>
                    </button>
                    <div class="faq-content hidden px-5 pb-5 text-xs text-gray-400 leading-relaxed border-t border-gray-800/50 pt-3">
                        Да! Итоговая стоимость работ и материалов фиксируется в договоре и не подлежит изменению. Если мы ошиблись в просчетах — доплачиваем из своего бюджета.
                    </div>
                </div>

                <!-- FAQ 3 -->
                <div class="glass-card rounded-xl overflow-hidden border border-gray-800">
                    <button class="faq-btn w-full p-5 text-left font-bold text-white flex justify-between items-center text-sm focus:outline-none">
                        <span>Что делать, если задержите сроки?</span>
                        <i class="fa-solid fa-chevron-down text-brand-accent transition-transform duration-300"></i>
                    </button>
                    <div class="faq-content hidden px-5 pb-5 text-xs text-gray-400 leading-relaxed border-t border-gray-800/50 pt-3">
                        В договоре прописан штраф за каждый день просрочки. Мы материально заинтересованы в том, чтобы сдать объект вовремя или раньше графиков.
                    </div>
                </div>

                <!-- FAQ 4 -->
                <div class="glass-card rounded-xl overflow-hidden border border-gray-800">
                    <button class="faq-btn w-full p-5 text-left font-bold text-white flex justify-between items-center text-sm focus:outline-none">
                        <span>Могу ли я сам закупать материалы?</span>
                        <i class="fa-solid fa-chevron-down text-brand-accent transition-transform duration-300"></i>
                    </button>
                    <div class="faq-content hidden px-5 pb-5 text-xs text-gray-400 leading-relaxed border-t border-gray-800/50 pt-3">
                        Конечно. Вы можете самостоятельно покупать чистовые отделочные материалы. При этом мы предоставляем список оптовых партнеров, где вы сможете воспользоваться нашей корпоративной скидкой.
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 9. CONTACT FORM SECTION -->
    <section id="contact" class="py-20 bg-brand-surface/80 border-t border-gray-800/80">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                
                <!-- Info Column -->
                <div class="lg:col-span-5 space-y-6">
                    <h2 class="text-3xl sm:text-4xl font-black text-white">Готовы преобразить ваше жильё?</h2>
                    <p class="text-gray-400 text-sm leading-relaxed">Оставьте заявку прямо сейчас. Мы перезвоним в течение 10 минут, ответим на все вопросы и забронируем за вами бесплатный выезд замерщика со скидкой 10%.</p>

                    <div class="space-y-4 pt-4">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-brand-card border border-gray-800 flex items-center justify-center text-brand-accent text-lg">
                                <i class="fa-solid fa-phone"></i>
                            </div>
                            <div>
                                <div class="text-xs text-gray-500">Телефон для связи</div>
                                <div class="text-white font-bold text-base">+7 (495) 999-88-77</div>
                            </div>
                        </div>

                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-brand-card border border-gray-800 flex items-center justify-center text-brand-accent text-lg">
                                <i class="fa-solid fa-location-dot"></i>
                            </div>
                            <div>
                                <div class="text-xs text-gray-500">Наш офис</div>
                                <div class="text-white font-bold text-base">Москва, Пресненская наб., 12 (Башня Федерация)</div>
                            </div>
                        </div>

                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-brand-card border border-gray-800 flex items-center justify-center text-brand-accent text-lg">
                                <i class="fa-solid fa-envelope"></i>
                            </div>
                            <div>
                                <div class="text-xs text-gray-500">Электронная почта</div>
                                <div class="text-white font-bold text-base">hello@eliterenovation.ru</div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Contact Form -->
                <div class="lg:col-span-7">
                    <div class="glass-card p-8 rounded-2xl border-brand-accent/30 shadow-2xl">
                        <form id="contact-form" onsubmit="handleFormSubmit(event)" class="space-y-5">
                            <div class="grid sm:grid-cols-2 gap-5">
                                <div>
                                    <label class="block text-xs font-bold text-gray-300 mb-2">Ваше имя *</label>
                                    <input type="text" required placeholder="Константин" class="w-full bg-brand-dark/90 border border-gray-700 rounded-xl px-4 py-3.5 text-sm text-white focus:outline-none focus:border-brand-accent">
                                </div>
                                <div>
                                    <label class="block text-xs font-bold text-gray-300 mb-2">Телефон *</label>
                                    <input type="tel" required placeholder="+7 (___) ___-__-__" class="w-full bg-brand-dark/90 border border-gray-700 rounded-xl px-4 py-3.5 text-sm text-white focus:outline-none focus:border-brand-accent">
                                </div>
                            </div>

                            <div>
                                <label class="block text-xs font-bold text-gray-300 mb-2">Вид недвижимости / услуга</label>
                                <select class="w-full bg-brand-dark/90 border border-gray-700 rounded-xl px-4 py-3.5 text-sm text-gray-300 focus:outline-none focus:border-brand-accent">
                                    <option>Капитальный ремонт квартиры</option>
                                    <option>Дизайнерский ремонт с 3D-проектом</option>
                                    <option>Косметический ремонт</option>
                                    <option>Отделка загородного дома</option>
                                </select>
                            </div>

                            <div>
                                <label class="block text-xs font-bold text-gray-300 mb-2">Комментарий (площадь, ЖК, пожелания)</label>
                                <textarea rows="3" placeholder="Квартира 80 м² в ЖК «Пресня Сити»..." class="w-full bg-brand-dark/90 border border-gray-700 rounded-xl px-4 py-3.5 text-sm text-white focus:outline-none focus:border-brand-accent"></textarea>
                            </div>

                            <button type="submit" class="w-full bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-extrabold py-4 rounded-xl shadow-xl shadow-amber-500/20 transition duration-200 text-xs uppercase tracking-wider">
                                Забронировать бесплатный замер
                            </button>

                            <p class="text-[11px] text-gray-500 text-center">Отправляя форму, вы даете согласие на обработку персональных данных</p>
                        </form>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 10. FOOTER -->
    <footer class="bg-brand-dark border-t border-gray-800/80 py-10 text-xs text-gray-500">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row justify-between items-center gap-6">
            <div class="flex items-center gap-3">
                <div class="w-8 h-8 rounded-lg bg-brand-accent text-black font-extrabold flex items-center justify-center text-sm">
                    <i class="fa-solid fa-crown"></i>
                </div>
                <div>
                    <span class="font-black text-white">ELITE RENOVATION</span>
                    <span class="block text-[10px] text-gray-500">© 2026. Все права защищены.</span>
                </div>
            </div>

            <div class="flex space-x-6 text-gray-400 text-lg">
                <a href="#" class="hover:text-brand-accent transition"><i class="fa-brands fa-telegram"></i></a>
                <a href="#" class="hover:text-brand-accent transition"><i class="fa-brands fa-whatsapp"></i></a>
                <a href="#" class="hover:text-brand-accent transition"><i class="fa-brands fa-vk"></i></a>
                <a href="#" class="hover:text-brand-accent transition"><i class="fa-brands fa-youtube"></i></a>
            </div>
        </div>
    </footer>

    <!-- SUCCESS MODAL -->
    <div id="modal-backdrop" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
        <div class="glass-card max-w-md w-full p-8 rounded-2xl relative text-center border-brand-accent/40 space-y-4 shadow-2xl">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="w-16 h-16 bg-emerald-500/20 border border-emerald-500/40 text-emerald-400 rounded-full flex items-center justify-center mx-auto text-2xl">
                <i class="fa-solid fa-check"></i>
            </div>
            <h3 class="text-xl font-bold text-white" id="modal-title">Заявка успешно отправлена!</h3>
            <p class="text-xs text-gray-300">Наш инженер свяжется с вами в течение 10 минут для уточнения деталей и расчета сметы.</p>
            <button onclick="closeModal()" class="w-full bg-brand-accent text-black font-bold py-3 rounded-xl mt-2 text-xs uppercase tracking-wider">
                Понятно
            </button>
        </div>
    </div>

    <!-- LIGHTBOX MODAL FOR PORTFOLIO -->
    <div id="image-modal" class="fixed inset-0 bg-black/90 backdrop-blur-md z-50 hidden flex items-center justify-center p-4" onclick="closeImageModal()">
        <div class="relative max-w-4xl w-full" onclick="event.stopPropagation()">
            <button onclick="closeImageModal()" class="absolute -top-10 right-0 text-white hover:text-brand-accent text-2xl">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <img id="lightbox-img" src="" class="w-full h-auto max-h-[80vh] object-contain rounded-xl border border-gray-800">
            <div id="lightbox-caption" class="text-center text-sm font-bold text-white mt-3"></div>
        </div>
    </div>

    <!-- JAVASCRIPT CODE -->
    <script>
        // --- 1. Mobile Menu Toggle ---
        const mobileBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');
        mobileBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // --- 2. Interactive Before/After Image Comparison Slider ---
        const baSlider = document.getElementById('hero-ba-slider');
        const baAfterLayer = document.getElementById('ba-after-layer');
        const baAfterImg = document.getElementById('ba-after-img');
        const baHandleLine = document.getElementById('ba-handle-line');

        function updateSliderWidth() {
            if(baSlider && baAfterImg) {
                baAfterImg.style.width = baSlider.offsetWidth + 'px';
            }
        }
        window.addEventListener('resize', updateSliderWidth);
        updateSliderWidth();

        let isDragging = false;
        if(baSlider) {
            const moveSlider = (x) => {
                const rect = baSlider.getBoundingClientRect();
                let position = x - rect.left;
                if (position < 0) position = 0;
                if (position > rect.width) position = rect.width;
                const percentage = (position / rect.width) * 100;
                baAfterLayer.style.width = percentage + '%';
                baHandleLine.style.left = percentage + '%';
            };

            baSlider.addEventListener('mousedown', () => isDragging = true);
            window.addEventListener('mouseup', () => isDragging = false);
            window.addEventListener('mousemove', (e) => {
                if (!isDragging) return;
                moveSlider(e.clientX);
            });

            baSlider.addEventListener('touchstart', () => isDragging = true);
            window.addEventListener('touchend', () => isDragging = false);
            window.addEventListener('touchmove', (e) => {
                if (!isDragging) return;
                moveSlider(e.touches[0].clientX);
            });
        }

        // --- 3. Interactive Renovation Calculator ---
        let currentHousingCoeff = 1.0;
        let currentRepairPrice = 22000;
        let currentArea = 75;

        const areaRange = document.getElementById('area-range');
        const areaVal = document.getElementById('area-val');
        const totalPriceEl = document.getElementById('total-price');
        const calcDaysEl = document.getElementById('calc-days');

        // Housing Type Selection
        document.querySelectorAll('.calc-housing').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.calc-housing').forEach(b => b.classList.remove('active-calc-option'));
                this.classList.add('active-calc-option');
                currentHousingCoeff = parseFloat(this.getAttribute('data-housing'));
                calculateTotal();
            });
        });

        // Repair Class Selection
        document.querySelectorAll('.calc-repair').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.calc-repair').forEach(b => b.classList.remove('active-calc-option'));
                this.classList.add('active-calc-option');
                currentRepairPrice = parseFloat(this.getAttribute('data-price'));
                calculateTotal();
            });
        });

        // Area Slider Listener
        if(areaRange) {
            areaRange.addEventListener('input', function() {
                currentArea = parseInt(this.value);
                areaVal.textContent = currentArea;
                calculateTotal();
            });
        }

        // Addon Checkboxes
        document.querySelectorAll('.calc-addon').forEach(cb => {
            cb.addEventListener('change', calculateTotal);
        });

        function calculateTotal() {
            let addonsPrice = 0;
            document.querySelectorAll('.calc-addon:checked').forEach(cb => {
                addonsPrice += parseFloat(cb.getAttribute('data-addon'));
            });

            const baseCost = (currentRepairPrice + addonsPrice) * currentArea * currentHousingCoeff;
            const finalCost = Math.round(baseCost);

            // Format Currency Output
            totalPriceEl.textContent = new Intl.NumberFormat('ru-RU').format(finalCost) + ' ₽';

            // Calculate Estimated Days
            let days = Math.round(currentArea * 0.7 + 20);
            calcDaysEl.textContent = `${days}-${days + 15} дней`;
        }

        // --- 4. Portfolio Filters ---
        const filterBtns = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');

        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                filterBtns.forEach(b => {
                    b.classList.remove('bg-brand-accent', 'text-black');
                    b.classList.add('bg-brand-card', 'text-gray-300');
                });
                btn.classList.add('bg-brand-accent', 'text-black');
                btn.classList.remove('bg-brand-card', 'text-gray-300');

                const filter = btn.getAttribute('data-filter');
                portfolioItems.forEach(item => {
                    if (filter === 'all' || item.getAttribute('data-category') === filter) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // --- 5. FAQ Accordion ---
        document.querySelectorAll('.faq-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                const content = btn.nextElementSibling;
                const icon = btn.querySelector('i');
                content.classList.toggle('hidden');
                icon.classList.toggle('rotate-180');
            });
        });

        // --- 6. Modal Functions ---
        const modalBackdrop = document.getElementById('modal-backdrop');
        const modalTitle = document.getElementById('modal-title');

        function openModal(title = 'Заявка принята!') {
            modalTitle.textContent = title;
            modalBackdrop.classList.remove('hidden');
        }

        function closeModal() {
            modalBackdrop.classList.add('hidden');
        }

        function handleFormSubmit(e) {
            e.preventDefault();
            openModal('Спасибо! Заявка отправлена');
            e.target.reset();
        }

        // Lightbox Image Preview
        const imageModal = document.getElementById('image-modal');
        const lightboxImg = document.getElementById('lightbox-img');
        const lightboxCaption = document.getElementById('lightbox-caption');

        function openImageModal(src, caption) {
            lightboxImg.src = src;
            lightboxCaption.textContent = caption;
            imageModal.classList.remove('hidden');
        }

        function closeImageModal() {
            imageModal.classList.add('hidden');
        }
    </script>
</body>
</html>

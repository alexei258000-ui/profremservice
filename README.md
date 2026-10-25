<html lang="ru" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Renovation — Премиальный ремонт квартир и домов под ключ в Москве</title>
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
                            accent: '#D4AF37',
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
                    <a href="#process" class="hover:text-brand-accent transition-colors">Этапы</a>
                    <a href="#reviews" class="hover:text-brand-accent transition-colors">Отзывы</a>
                    <a href="#contact" class="hover:text-brand-accent transition-colors">Контакты</a>
                </nav>

                <!-- Phone & CTA Button -->
                <div class="hidden sm:flex items-center space-x-5">
                    <a href="tel:+74959998877" class="text-right">
                        <div class="text-sm font-extrabold text-white hover:text-brand-accent transition-colors">+7 (495) 999-88-77</div>
                        <div class="text-[10px] text-emerald-400 flex items-center justify-end gap-1 font-medium">
                            <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span> Работаем ежедневно
                        </div>
                    </a>

                    <button type="button" onclick="openModal('Заказать обратный звонок')" class="cursor-pointer bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-bold px-5 py-2.5 rounded-xl shadow-lg shadow-amber-500/20 transition-all hover:scale-105 active:scale-95 text-xs uppercase tracking-wider z-10">
                        Заказать звонок
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <div class="lg:hidden flex items-center gap-3">
                    <button type="button" id="mobile-menu-btn" onclick="toggleMobileMenu()" class="cursor-pointer text-gray-300 hover:text-white p-2">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden lg:hidden bg-brand-dark/95 backdrop-blur-xl border-b border-gray-800 px-6 pt-4 pb-6 space-y-3">
            <a href="#services" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Услуги</a>
            <a href="#calculator" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Калькулятор</a>
            <a href="#portfolio" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Портфолио</a>
            <a href="#process" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Этапы</a>
            <a href="#reviews" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2 border-b border-gray-800/50">Отзывы</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-brand-accent py-2">Контакты</a>
            <div class="pt-4 border-t border-gray-800 space-y-2">
                <button type="button" onclick="openModal('Заказать быстрый звонок'); toggleMobileMenu();" class="cursor-pointer w-full bg-brand-accent text-black font-bold py-3 rounded-xl uppercase text-xs tracking-wider">
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
                        Реализуем интерьерные решения любой сложности. Расчёт точной сметы за 1 минуту, фиксированная цена без скрытых переплат и закупка материалов по оптовым ценам.
                    </p>

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
                </div>

                <!-- Before / After Slider -->
                <div class="lg:col-span-5">
                    <div class="glass-card p-4 rounded-2xl shadow-2xl relative">
                        <div class="ba-container h-80 sm:h-96 w-full relative">
                            <img src="https://images.unsplash.com/photo-1581858726788-75bc0f6a952d?auto=format&fit=crop&w=1000&q=80" alt="До" class="absolute inset-0 w-full h-full object-cover">
                            <span class="absolute top-4 right-4 bg-black/80 text-white text-xs px-3 py-1 rounded-full backdrop-blur-md font-bold">ДО</span>

                            <div class="ba-img-after" style="width: 50%;">
                                <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=1000&q=80" alt="После" class="absolute top-0 left-0 max-w-none h-full object-cover">
                                <span class="absolute top-4 left-4 bg-brand-accent text-black font-extrabold text-xs px-3 py-1 rounded-full shadow-lg">ПОСЛЕ</span>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- SERVICES SECTION -->
    <section id="services" class="py-20 bg-brand-surface/60 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Наши направления</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Виды ремонта и отделки</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-paint-roller"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Косметический</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Быстрое обновление интерьера: выравнивание и покраска стен, замена покрытий.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 12 000 ₽/м²</div>
                        <button type="button" onclick="openModal('Косметический ремонт')" class="cursor-pointer w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between relative border-brand-accent/40">
                    <span class="absolute -top-3 right-4 bg-brand-accent text-black font-extrabold text-[10px] uppercase tracking-wider px-3 py-1 rounded-full">Популярный</span>
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/20 border border-brand-accent text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-hammer"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Капитальный</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Полная замена сетей, штукатурка по маякам, стяжка пола и отделка.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 22 000 ₽/м²</div>
                        <button type="button" onclick="openModal('Капитальный ремонт')" class="cursor-pointer w-full py-2.5 bg-brand-accent hover:bg-brand-accentHover text-xs font-bold text-black rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-compass-drafting"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Дизайнерский</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Ремонт по уникальному 3D-проекту с авторским надзором.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 35 000 ₽/м²</div>
                        <button type="button" onclick="openModal('Дизайнерский ремонт')" class="cursor-pointer w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>

                <div class="glass-card p-6 rounded-2xl flex flex-col justify-between">
                    <div>
                        <div class="w-12 h-12 rounded-xl bg-brand-accent/10 border border-brand-accent/30 text-brand-accent flex items-center justify-center font-bold text-xl mb-6">
                            <i class="fa-solid fa-house-chimney-window"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Ремонт домов</h3>
                        <p class="text-gray-400 text-xs leading-relaxed mb-6">Комплексная отделка коттеджей и таунхаусов.</p>
                    </div>
                    <div>
                        <div class="text-brand-accent font-extrabold text-lg mb-4">от 28 000 ₽/м²</div>
                        <button type="button" onclick="openModal('Ремонт домов')" class="cursor-pointer w-full py-2.5 border border-gray-700 hover:border-brand-accent text-xs font-semibold text-white hover:text-brand-accent rounded-xl transition-all">Заказать расчёт</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CALCULATOR SECTION -->
    <section id="calculator" class="py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Онлайн калькулятор</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Рассчитайте стоимость сметы</p>
            </div>

            <div class="grid lg:grid-cols-12 gap-8 items-start">
                
                <div class="lg:col-span-8 glass-card p-6 sm:p-8 rounded-2xl space-y-8">
                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-4">1. Тип недвижимости</label>
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                            <button type="button" class="cursor-pointer calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all active-calc-option" data-housing="1" onclick="selectCalcOption(this, 'calc-housing')">
                                <i class="fa-solid fa-building text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Новостройка</div>
                            </button>
                            <button type="button" class="cursor-pointer calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-housing="1.15" onclick="selectCalcOption(this, 'calc-housing')">
                                <i class="fa-solid fa-house-chimney text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Вторичка</div>
                            </button>
                            <button type="button" class="cursor-pointer calc-btn calc-housing p-4 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-housing="1.25" onclick="selectCalcOption(this, 'calc-housing')">
                                <i class="fa-solid fa-house text-brand-accent text-xl mb-2 block"></i>
                                <div class="font-bold text-white text-sm">Коттедж / Дом</div>
                            </button>
                        </div>
                    </div>

                    <div>
                        <label class="block text-sm font-bold text-gray-200 mb-4">2. Класс ремонта</label>
                        <div class="grid grid-cols-1 sm:grid-cols-4 gap-3">
                            <button type="button" class="cursor-pointer calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="12000" onclick="selectCalcOption(this, 'calc-repair')">
                                <div class="font-bold text-white text-xs">Косметический</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">12 000 ₽/м²</div>
                            </button>
                            <button type="button" class="cursor-pointer calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all active-calc-option" data-price="22000" onclick="selectCalcOption(this, 'calc-repair')">
                                <div class="font-bold text-white text-xs">Капитальный</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">22 000 ₽/м²</div>
                            </button>
                            <button type="button" class="cursor-pointer calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="35000" onclick="selectCalcOption(this, 'calc-repair')">
                                <div class="font-bold text-white text-xs">Дизайнерский</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">35 000 ₽/м²</div>
                            </button>
                            <button type="button" class="cursor-pointer calc-btn calc-repair p-3.5 rounded-xl border border-gray-800 bg-brand-dark/60 text-left transition-all" data-price="50000" onclick="selectCalcOption(this, 'calc-repair')">
                                <div class="font-bold text-white text-xs">Премиум</div>
                                <div class="text-brand-accent font-extrabold text-xs mt-2">50 000 ₽/м²</div>
                            </button>
                        </div>
                    </div>

                    <div>
                        <div class="flex justify-between items-center mb-3">
                            <label class="text-sm font-bold text-gray-200">3. Площадь помещения</label>
                            <span class="text-2xl font-black text-brand-accent"><span id="area-val">75</span> м²</span>
                        </div>
                        <input type="range" id="area-range" min="20" max="300" value="75" oninput="updateCalculator()" class="w-full cursor-pointer">
                    </div>
                </div>

                <div class="lg:col-span-4 glass-card p-6 sm:p-8 rounded-2xl border-brand-accent/40 space-y-6 sticky top-28">
                    <h3 class="text-lg font-extrabold text-white border-b border-gray-800 pb-4">Предварительная смета</h3>
                    <div class="pt-4 border-t border-gray-800">
                        <span class="text-xs text-gray-400 block uppercase font-semibold">Итоговая стоимость:</span>
                        <div id="total-price" class="text-3xl sm:text-4xl font-black gold-gradient-text my-2">
                            1 650 000 ₽
                        </div>
                    </div>
                    <button type="button" onclick="submitCalculatorLead()" class="cursor-pointer w-full bg-gradient-to-r from-brand-accent to-amber-600 hover:from-brand-accentHover hover:to-amber-700 text-black font-extrabold py-4 rounded-xl shadow-lg shadow-amber-500/20 uppercase tracking-wider text-xs transition-all hover:scale-105">
                        Оставить заявку
                    </button>
                </div>

            </div>
        </div>
    </section>

    <!-- PORTFOLIO SECTION -->
    <section id="portfolio" class="py-20 bg-brand-surface/60 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-bold text-brand-accent uppercase tracking-widest mb-2">Наши работы</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-white">Реализованные проекты</p>
            </div>
            <div class="grid md:grid-cols-3 gap-6">
                <div class="glass-card rounded-2xl overflow-hidden">
                    <div class="h-60 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Проект">
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-bold text-white mb-1">Апартаменты 110 м²</h3>
                    </div>
                </div>
                <div class="glass-card rounded-2xl overflow-hidden">
                    <div class="h-60 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Проект">
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-bold text-white mb-1">Квартира 85 м²</h3>
                    </div>
                </div>
                <div class="glass-card rounded-2xl overflow-hidden">
                    <div class="h-60 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1600566753376-12c8ab7fb75b?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Проект">
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-bold text-white mb-1">Коттедж 240 м²</h3>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER / CONTACTS -->
    <footer id="contact" class="py-16 bg-brand-surface/80 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center sm:text-left flex flex-col sm:flex-row justify-between items-center gap-6">
            <div>
                <span class="text-2xl font-black tracking-wider gold-gradient-text">ELITE RENOVATION</span>
                <p class="text-gray-400 text-xs mt-1">Премиальный ремонт квартир и домов в Москве</p>
            </div>
            <div class="flex items-center gap-6">
                <a href="tel:+74959998877" class="text-white font-bold hover:text-brand-accent transition">+7 (495) 999-88-77</a>
                <button type="button" onclick="openModal('Заказать звонок из футера')" class="cursor-pointer bg-brand-accent text-black font-bold px-4 py-2 rounded-xl text-xs uppercase tracking-wider">
                    Заказать звонок
                </button>
            </div>
        </div>
    </footer>

    <!-- MODAL FORM -->
    <div id="modalForm" class="hidden fixed inset-0 z-50 bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-brand-card rounded-2xl border border-brand-accent/30 max-w-md w-full p-6 relative shadow-2xl">
            <button type="button" onclick="closeModal()" class="cursor-pointer absolute top-4 right-4 text-gray-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <h3 id="modalFormTitle" class="text-lg font-bold text-white mb-4">Заказать звонок</h3>
            <form onsubmit="handleWebsiteSubmit(event)" class="space-y-4">
                <input type="hidden" id="formSubject" value="Заявка с сайта">
                <div>
                    <input type="text" id="custName" required placeholder="Ваше имя" class="w-full px-4 py-2 bg-brand-dark border border-gray-800 rounded-xl text-sm text-white focus:border-brand-accent outline-none">
                </div>
                <div>
                    <input type="tel" id="custPhone" required placeholder="Ваш телефон" class="w-full px-4 py-2 bg-brand-dark border border-gray-800 rounded-xl text-sm text-white focus:border-brand-accent outline-none">
                </div>
                <button type="submit" class="cursor-pointer w-full bg-brand-accent text-black font-extrabold py-3 rounded-xl uppercase tracking-wider text-xs">
                    Отправить заявку
                </button>
            </form>
        </div>
    </div>

    <!-- SCRIPTS -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            closeModal();
            updateCalculator();
        });

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

        function handleWebsiteSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('custName').value;
            const phone = document.getElementById('custPhone').value;
            const subject = document.getElementById('formSubject').value;

            addLeadToCRM(name, phone, subject);
            closeModal();
            alert('Спасибо! Ваша заявка успешно отправлена.');
            e.target.reset();
        }

        function updateCalculator() {
            const areaRange = document.getElementById('area-range');
            const areaVal = document.getElementById('area-val');
            const totalPrice = document.getElementById('total-price');
            
            if (!areaRange || !areaVal || !totalPrice) return;

            const area = areaRange.value;
            areaVal.innerText = area;

            const activeHousing = document.querySelector('.calc-housing.active-calc-option');
            const activeRepair = document.querySelector('.calc-repair.active-calc-option');

            const selectedHousing = parseFloat(activeHousing ? activeHousing.dataset.housing : 1);
            const selectedRepair = parseFloat(activeRepair ? activeRepair.dataset.price : 22000);

            const total = Math.round(area * selectedRepair * selectedHousing);
            totalPrice.innerText = total.toLocaleString('ru-RU') + ' ₽';
        }

        function selectCalcOption(btn, groupClass) {
            document.querySelectorAll('.' + groupClass).forEach(b => b.classList.remove('active-calc-option'));
            btn.classList.add('active-calc-option');
            updateCalculator();
        }

        function submitCalculatorLead() {
            const area = document.getElementById('area-range').value;
            const price = document.getElementById('total-price').innerText;
            openModal('Заявка с калькулятора (' + area + ' м², ' + price + ')');
        }

        function addLeadToCRM(name, phone, service) {
            let leads = JSON.parse(localStorage.getItem('crm_leads')) || [
                { id: 1, name: 'Михаил Решетов', phone: '+7 (926) 111-22-33', service: 'Капитальный ремонт', date: '2026-06-06 12:40' }
            ];

            const now = new Date();
            const dateStr = now.toISOString().slice(0,10) + ' ' + now.toTimeString().slice(0,5);
            
            leads.unshift({ id: Date.now(), name, phone, service, date: dateStr, status: 'new', notes: '' });
            
            localStorage.setItem('crm_leads', JSON.stringify(leads));
        }
    </script>
</body>
</html>

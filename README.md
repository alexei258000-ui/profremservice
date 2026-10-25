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

    <!-- 1. HEADER NAVIGATION -->
    <header class="fixed top-0 left-0 w-full z-50 glass-nav transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Logo

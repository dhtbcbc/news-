<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر الشعبي العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Tajawal for Arabic support -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <!-- Font Awesome for social media icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" xintegrity="sha512-R4R/Y8A+Kz/q3F+G9+Y8zF1+W+g7/Q/n6Gz+g/Y7+W8/W9+N7/X6+T7/G6+Z9+F8/V7/T6/F5/R4/V3/T2/G1/Z0/A9/B8/C7/D6/E5/F4/I3/J2/K1/L0/M9/N8/O7/P6/Q5/R4/S3/T2/U1/V0/W9/X8/Y7/Z6/a5/b4/c3/d2/e1/f0/g9/h8/i7/j6/k5/l4/m3/n2/o1/p0/q9/r8/s7/t6/u5/v4/w3/x2/y1/z0/A9/B8/C7/D6/E5/F4/G3/H2/I1/J0/K9/L8/M7/N6/O5/P4/Q3/R2/S1/T0/U9/V8/W7/X6/Y5/Z4/a3/b2/c1/d0/e9/f8/g7/h6/i5/j4/k3/l2/m1/n0/o9/p8/q7/r6/s5/t4/u3/v2/w3/x2/y1/z0" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        /* Global Styles */
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #FAF9F6; /* Light beige/off-white background */
            color: #333; /* Soft dark grey for general text */
            line-height: 1.8; /* Increased line height for poetry readability */
            scroll-behavior: smooth; /* Smooth scrolling for anchor links */
        }

        /* Utility for delaying animations */
        .animation-delay-100 { animation-delay: 0.1s; }
        .animation-delay-200 { animation-delay: 0.2s; }
        .animation-delay-300 { animation-delay: 0.3s; }
        .animation-delay-400 { animation-delay: 0.4s; }

        /* Keyframe for simple fade-in (used for hero text) */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeIn 0.8s ease-out forwards;
            opacity: 0; /* Hidden by default */
        }

        /* Header Frame Styling */
        .header-frame {
            background-color: #F4F1EE; /* Slightly darker background for the frame */
            border-radius: 1rem; /* Rounded corners for the frame */
            padding: 1.25rem 2.5rem; /* More padding for a distinct frame */
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08); /* Soft shadow for depth */
            max-width: 90%; /* Max width for the frame */
            margin: 0 auto; /* Center the frame */
        }

        /* Header Show/Hide Animation */
        #main-header {
            transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
        }
        .header-hidden {
            transform: translateY(-150%); /* Move further up to completely hide */
            opacity: 0;
        }
        .header-visible {
            transform: translateY(0);
            opacity: 1;
        }

        /* Smooth slide-in animation for cards */
        .fade-in-slide-rtl {
            opacity: 0;
            transform: translateX(20px); /* Start slightly to the right */
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .fade-in-slide-rtl.animate-in {
            opacity: 1;
            transform: translateX(0); /* Slide to original position */
        }

        /* Hover effects for navigation links */
        .nav-link {
            position: relative;
            color: #8B5E3C; /* Walnut brown for links */
            transition: color 0.3s ease-in-out;
        }
        .nav-link:hover {
            color: #FFA500; /* Warm orange on hover */
        }
        .nav-link::after {
            content: '';
            display: block;
            width: 0;
            height: 2px;
            background: #FFA500;
            transition: width 0.3s ease-out;
            position: absolute;
            bottom: -5px;
            right: 0; /* For RTL */
        }
        .nav-link:hover::after {
            width: 100%;
            left: 0; /* For RTL */
        }

        /* Button hover effect */
        .btn-primary {
            transition: background-color 0.3s ease-in-out, transform 0.2s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .btn-primary:hover {
            background-color: #EEDC82; /* Muted yellow on hover */
            transform: translateY(-2px); /* Slight lift */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Soft shadow on hover */
        }

        /* Simple search input focus animation */
        .search-input:focus {
            border-color: #FFA500;
            box-shadow: 0 0 0 3px rgba(255, 165, 0, 0.2); /* Soft orange glow */
            outline: none;
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        /* Card hover effect for poems/poets */
        .poetry-card, .poet-entry {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .poetry-card:hover, .poet-entry:hover {
            transform: translateY(-5px); /* Slight lift */
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.08); /* More pronounced shadow */
        }

        /* Specific style for poem text to ensure line breaks are preserved */
        .poem-text {
            white-space: pre-line; /* Preserves line breaks from content */
            font-size: 1rem;
            color: #4a4a4a;
            margin-bottom: 1rem;
        }

        /* Poet entry styling (removed box) */
        .poet-entry {
            background-color: #FFF;
            border-radius: 0.5rem;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05); /* Lighter shadow for a "flatter" look */
        }
        .poet-entry img {
            border-radius: 9999px; /* Make image circular */
            width: 120px; /* Fixed size for consistency */
            height: 120px;
            object-fit: cover;
            margin: 0 auto 0.75rem auto; /* Center and add margin */
            border: 3px solid #FFA500; /* Orange border for highlight */
        }

        /* Responsive adjustments for mobile and tablet */
        @media (max-width: 768px) {
            .header-frame {
                padding: 1rem; /* Smaller padding on mobile */
                max-width: 95%; /* Wider on mobile */
            }
            .header-frame .flex-col {
                flex-direction: column;
            }
            .header-frame .md\:flex-row {
                flex-direction: column;
                align-items: center;
            }
            .header-frame .md\:space-x-6 {
                margin-top: 1rem;
                justify-content: center;
            }
            .header-frame .text-3xl {
                font-size: 1.75rem; /* Smaller logo text on mobile */
            }
            .nav-link {
                font-size: 1rem; /* Smaller nav links on mobile */
            }
            .search-input {
                padding: 0.75rem; /* Smaller search input padding */
                font-size: 1rem; /* Smaller search input text */
            }
            #hero h1 {
                font-size: 3rem; /* Smaller hero title on mobile */
            }
            #hero p {
                font-size: 1.25rem; /* Smaller hero subtitle on mobile */
            }
            .btn-primary {
                font-size: 1.1rem; /* Smaller button text on mobile */
                padding: 0.75rem 2rem; /* Smaller button padding */
            }
            .poetry-card .p-6 {
                padding: 1rem; /* Smaller card padding on mobile */
            }
            .poetry-card h3 {
                font-size: 1.5rem; /* Smaller card title on mobile */
            }
            .text-5xl { /* Section titles */
                font-size: 2.5rem;
            }
            .text-4xl { /* Newsletter title */
                font-size: 2rem;
            }
            .text-xl { /* Newsletter subtitle */
                font-size: 1rem;
            }
            .footer-links {
                flex-direction: column;
                gap: 0.5rem;
            }
            .poem-text {
                font-size: 0.9rem; /* Slightly smaller poem text on mobile */
            }
            .poet-entry img {
                width: 90px;
                height: 90px;
            }
        }

        /* Adjustments for tablets (iPad) */
        @media (min-width: 769px) and (max-width: 1024px) {
            .header-frame {
                padding: 1.5rem 3rem;
            }
            #hero h1 {
                font-size: 4.5rem;
            }
            #hero p {
                font-size: 2rem;
            }
            .poetry-card h3 {
                font-size: 1.75rem;
            }
            .text-5xl {
                font-size: 3.5rem;
            }
            .text-4xl {
                font-size: 2.5rem;
            }
            .text-xl {
                font-size: 1.15rem;
            }
        }
    </style>
</head>
<body>

    <!-- Header Section -->
    <header id="main-header" class="fixed top-4 left-1/2 -translate-x-1/2 w-full z-50 transition-all duration-300 ease-in-out header-visible">
        <div class="header-frame">
            <nav class="flex flex-col items-center">
                <!-- Logo and Navigation Links Row -->
                <div class="flex flex-col md:flex-row justify-between items-center w-full mb-4 md:mb-0">
                    <!-- Logo -->
                    <div>
                        <a href="#" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            موسوعة الشعر الشعبي العراقي
                        </a>
                    </div>
                    <!-- Navigation Bar -->
                    <ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">
                        <li><a href="#hero" class="nav-link text-lg font-medium">الرئيسية</a></li>
                        <li><a href="#poets-directory" class="nav-link text-lg font-medium">الشعراء</a></li>
                        <li><a href="#poetry-genres" class="nav-link text-lg font-medium">أنواع الشعر</a></li>
                        <li><a href="#contact-us" class="nav-link text-lg font-medium">تواصل معنا</a></li>
                    </ul>
                </div>
                <!-- Search Bar -->
                <div class="relative w-full mt-4">
                    <input type="text" id="searchInput" placeholder="ابحث عن شاعر أو قصيدة..." class="search-input w-full p-3 md:p-4 text-lg border border-gray-300 rounded-full focus:ring-0 text-right pr-12">
                    <button class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500 hover:text-orange-500 transition duration-300 text-xl" aria-label="بحث">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="relative bg-cover bg-center text-center flex flex-col items-center justify-center" style="background-color: #F4F1EE;">
        <div class="max-w-4xl px-4 py-20">
            <h1 class="text-6xl md:text-7xl font-extrabold text-gray-800 mb-6 leading-tight animate-fade-in">
                مرحبًا بك في <span class="text-orange-500">موسوعة الشعر الشعبي العراقي</span>
            </h1>
            <p class="text-2xl md:text-3xl text-gray-600 mb-10 animate-fade-in animation-delay-200">
                بوابة لأروع القصائد وأشهر الشعراء الذين خطوا تاريخ العراق بكلماتهم
            </p>
            <a href="#poets-directory" class="btn-primary bg-orange-500 text-white text-xl md:text-2xl font-semibold py-4 px-10 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 animate-fade-in animation-delay-400">
                ابدأ رحلتك الشعرية
            </a>
        </div>
    </section>

    <!-- Poets Directory Section -->
    <section id="poets-directory" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">الشعراء العراقيون</h2>
        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
            <!-- Poet Link 1: سمير صبيح -->
            <a href="#samir-sbeih-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl">
                <img src="https://placehold.co/120x120/8B5E3C/FAF9F6?text=سمير+صبيح" alt="صورة الشاعر سمير صبيح" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">سمير صبيح</p>
            </a>
            <!-- Poet Link 2: جبار رشيد -->
            <a href="#jabbar-rasheed-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-100">
                <img src="https://placehold.co/120x120/EEDC82/8B5E3C?text=جبار+رشيد" alt="صورة الشاعر جبار رشيد" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">جبار رشيد</p>
            </a>
            <!-- Poet Link 3: علي رشم -->
            <a href="#ali-rasham-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-200">
                <img src="https://placehold.co/120x120/FFA500/FAF9F6?text=علي+رشم" alt="صورة الشاعر علي رشم" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">علي رشم</p>
            </a>
            <!-- Poet Link 4: مظفر النواب -->
            <a href="#muzaffar-alnawab-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-300">
                <img src="https://placehold.co/120x120/F4F1EE/8B5E3C?text=مظفر+النواب" alt="صورة الشاعر مظفر النواب" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">مظفر النواب</p>
            </a>
            <!-- Poet Link 5: كاظم اسماعيل الكاطع -->
            <a href="#kadhim-alkatea-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-400">
                <img src="https://placehold.co/120x120/8B5E3C/EEDC82?text=كاظم+الكاطع" alt="صورة الشاعر كاظم اسماعيل الكاطع" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">كاظم اسماعيل الكاطع</p>
            </a>
            <!-- Poet Link 6: عريان السيد خلف -->
            <a href="#arian-alsayed-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-500">
                <img src="https://placehold.co/120x120/FFA500/8B5E3C?text=عريان+السيد+خلف" alt="صورة الشاعر عريان السيد خلف" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">عريان السيد خلف</p>
            </a>
            <!-- Poet Link 7: ناظم الحاشي -->
            <a href="#nazem-alhashi-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-600">
                <img src="https://placehold.co/120x120/EEDC82/8B5E3C?text=ناظم+الحاشي" alt="صورة الشاعر ناظم الحاشي" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">ناظم الحاشي</p>
            </a>
            <!-- Poet Link 8: رحيم المالكي -->
            <a href="#raheem-almaliki-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-700">
                <img src="https://placehold.co/120x120/F4F1EE/8B5E3C?text=رحيم+المالكي" alt="صورة الشاعر رحيم المالكي" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">رحيم المالكي</p>
            </a>
            <!-- Poet Link 9: عبد الحسين الحلفي -->
            <a href="#abd-alhussein-alhalfy-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-800">
                <img src="https://placehold.co/120x120/8B5E3C/FAF9F6?text=عبد+الحسين+الحلفي" alt="صورة الشاعر عبد الحسين الحلفي" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">عبد الحسين الحلفي</p>
            </a>
            <!-- Poet Link 10: كريم العراقي -->
            <a href="#kareem-aliraqi-poems" class="poet-entry flex flex-col items-center justify-center p-4 rounded-lg hover:bg-orange-50 transition duration-300 fade-in-slide-rtl animation-delay-900">
                <img src="https://placehold.co/120x120/FFA500/8B5E3C?text=كريم+العراقي" alt="صورة الشاعر كريم العراقي" class="w-full h-56 object-cover rounded-t-lg" loading="lazy">
                <p class="text-lg font-semibold text-gray-800 mt-2">كريم العراقي</p>
            </a>
        </div>
    </section>

    <!-- Poetry Genres Section -->
    <section id="poetry-genres" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">أقسام الشعر الشعبي</h2>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Genre Card 1: شعر حب وغزل ورومانسي -->
            <a href="#love-romantic-poetry-list" class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl text-center p-6 flex flex-col items-center justify-center hover:bg-orange-50 transition duration-300">
                <img src="https://placehold.co/200x150/FFA500/FAF9F6?text=حب+وغزل" alt="شعر حب وغزل" class="w-full h-32 object-cover rounded-lg mb-4" loading="lazy">
                <h3 class="text-2xl font-semibold text-gray-800">شعر الحب والغزل والرومانسية</h3>
            </a>
            <!-- Genre Card 2: شعر جريء ووطني -->
            <a href="#bold-patriotic-poetry-list" class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100 text-center p-6 flex flex-col items-center justify-center hover:bg-orange-50 transition duration-300">
                <img src="https://placehold.co/200x150/8B5E3C/EEDC82?text=جريء+ووطني" alt="شعر جريء ووطني" class="w-full h-32 object-cover rounded-lg mb-4" loading="lazy">
                <h3 class="text-2xl font-semibold text-gray-800">شعر جريء ووطني</h3>
            </a>
            <!-- Genre Card 3: شعر اجتماعي وحكمة -->
            <a href="#social-wisdom-poetry-list" class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-200 text-center p-6 flex flex-col items-center justify-center hover:bg-orange-50 transition duration-300">
                <img src="https://placehold.co/200x150/EEDC82/8B5E3C?text=اجتماعي+وحكمة" alt="شعر اجتماعي وحكمة" class="w-full h-32 object-cover rounded-lg mb-4" loading="lazy">
                <h3 class="text-2xl font-semibold text-gray-800">شعر اجتماعي وحكمة</h3>
            </a>
        </div>
    </section>

    <!-- Specific Poet Sections (Virtual Pages for poets) -->
    <!-- Samir Sbeih Poems -->
    <section id="samir-sbeih-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر سمير صبيح</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">ليش تمشي؟</h4>
                    <div class="poem-text text-gray-800">
                        ليش تمشي؟ وادري عيونك تريدني،<br>
                        شگد ما مشيت بيا وطن... روحي تظل يمك.<br>
                        الدمعة بعيني ما تنشف،<br>
                        وبعدك أبد ما نمت ليلة.<br>
                        كل طيف يمر بيه، أحسبه إنت،<br>
                        وأركض وراه وألگاني وهم.<br>
                        يا ريت الزمن يرجع،<br>
                        وترجعلي ضحكة سنيني.
                    </div>
                </div>
            </div>
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا دنيا شبية</h4>
                    <div class="poem-text text-gray-800">
                        يا دنيا شبية ما تخلصين،<br>
                        ويا روحي شبيچ ما تفرحين.<br>
                        كل يوم يكبر جرحي بلياچ،<br>
                        وصار الضحك ما يلوگ لعيوني.<br>
                        أنا المكتوبلي أظل بهمومي،<br>
                        والحسرة بگلبي ما تفارگني.<br>
                        يا ريت الموت يجي ويخلصني،<br>
                        من دنيا ما بيها أي شي يسعدني.
                    </div>
                </div>
            </div>
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-200">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">ما ريدك</h4>
                    <div class="poem-text text-gray-800">
                        ما ريدك بعد لو صرت ملك الموت،<br>
                        ولتردلي ولا تسأل على حالي.<br>
                        كسرت گلبي وخذيت الروح مني،<br>
                        تاليها بعتني بأرخص ليالي.<br>
                        خليني وحيد، وحدي أحسنلي،<br>
                        الجرح يطيب لو صار وگته.<br>
                        عيني تشوفك بس گلبي ينساك،<br>
                        ما اريدك تجي، كافي العذاب.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Jabbar Rasheed Poems -->
    <section id="jabbar-rasheed-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر جبار رشيد</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا أول عشگ</h4>
                    <div class="poem-text text-gray-800">
                        يا أول عشگ حنّيتله وعيني بكتله دموع،<br>
                        يا آخر نفس بضلوعي ظل بيّه يروح ويعود.<br>
                        شلون أنسى الليالي البيها چنت وياك؟<br>
                        شلون أطرد خيالك من يجي بجروحي؟<br>
                        روحي بيك تتوسّل، تعال ارجعلي.<br>
                        عمري بدونك ما يسوى ولا يوم.<br>
                        يا بعد كل ناسي وهلي، يا أغلى من الروح،<br>
                        لو تدري شگد أحبك، ما تبتعد عني.
                    </div>
                </div>
            </div>
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا ليل الشوگ</h4>
                    <div class="poem-text text-gray-800">
                        يا ليل الشوگ، بيا درب وديتني،<br>
                        ودمعي يسيل على الخدين.<br>
                        تعبت روحي من كثر الونين،<br>
                        ومحد يگدر يفهمني يا ناس.<br>
                        أنا الماشي دروب الحب وحدي،<br>
                        وقلبي ينزف من كثر الجراح.<br>
                        يا دنيتي كافي هجر وبعد،<br>
                        ردولي حبيبي، كافي دموع.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Ali Rasham Poems -->
    <section id="ali-rasham-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشهيد الشاعر علي رشم</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">دمي يحكي</h4>
                    <div class="poem-text text-gray-800">
                        دمي يحكي قصة وطن،<br>
                        بيها التضحية صارت فن.<br>
                        ما خفت من الموت لحظة،<br>
                        روحي فدوة لتراب الوطن.<br>
                        لو كل قطرة دم تصير شراع،<br>
                        أوصلك يا عراق لأعلى مكان.<br>
                        أنا ابنك يا دجلة والفرات،<br>
                        ترابك أغلى من الذهب، يا أغلى الأوطان.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Muzaffar Al-Nawab Poems -->
    <section id="muzaffar-alnawab-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر مظفر النواب</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">ريحة خبز بالليل</h4>
                    <div class="poem-text text-gray-800">
                        ريحة خبز بالليل، تعاتبني،<br>
                        تگلي مر بيه. يا ريل العشگ،<br>
                        وين أخذتني يا ريل؟<br>
                        الناس نامت، وأنا عيني مفتوحة.<br>
                        يا هموم الدنيا، شكد كافية؟<br>
                        گوم أرحم گلبي، يا ليل.<br>
                        وين الفرح؟ وين السعادة؟<br>
                        بس حزن بگلبي، ما يروح.
                    </div>
                </div>
            </div>
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">وحق روحي</h4>
                    <div class="poem-text text-gray-800">
                        وحق روحي التذوبن بيك،<br>
                        ما بطلن من الدمع عيوني.<br>
                        گلبي الك وحدك ينبض،<                        وكل دگة بي تنادي باسمك.<br>
                        يا حلمي الجاي، يا كل عمري،<br>
                        بدونك دنيتي مو حلوة.<br>
                        خليني أعيش وياك،<br>
                        كل لحظة وكل سنين.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Kadhim Al-Katea Poems -->
    <section id="kadhim-alkatea-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر كاظم اسماعيل الكاطع</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا روحي العذبتها</h4>
                    <div class="poem-text text-gray-800">
                        يا روحي العذبتها، بيمن تاليها تروح،<br>
                        محد غيري يفهمك، يا كل الجروح.<br>
                        أنا اللي سهرت الليالي وياك،<br>
                        وعيني ما نامت بس تشوفك.<br>
                        كل كلمة منك، أحفظها بگلبي،<br>
                        وكل نظرة عينك، هي دوا روحي.<br>
                        لا تعوفني وحدي، يا أغلى ناسي،<br>
                        ترى بدونك، دنياي تصير ظلام.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Arian Al-Sayed Khalaf Poems -->
    <section id="arian-alsayed-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر عريان السيد خلف</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">كلشي منك حلو</h4>
                    <div class="poem-text text-gray-800">
                        كلشي منك حلو، حتى عذابك يا حبيبي،<br>
                        تظل بگلبي شعلة نار ما تطفي.<br>
                        يا أول عشگ، يا آخر محبة،<br>
                        روحي وروحي ليك تروح.<br>
                        شگد حاولت أنساك، ما گدرت،<br>
                        صورك بالبال، ما تفارگ عيني.<br>
                        أنا العايش على ذكرى حبك،<br>
                        وبدونك، دنيتي ما تسوى شي.
                    </div>
                </div>
            </div>
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا ديرتي</h4>
                    <div class="poem-text text-gray-800">
                        يا ديرتي الشالت هموم الناس،<br>
                        وجروحها ما طابت بيوم.<br>
                        كل بيت بيها قصة حزن،<br>
                        وكل روح بيها تشكي الظلوم.<br>
                        متى الفرح يجي لدروبها؟<br>
                        وتنسى المر وتعيش بيوم.<br>
                        هاي الناس الطيبة الفقيرة،<br>
                        بس رب العباد يدري بظروفها.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Nazem Al-Hashi Poems -->
    <section id="nazem-alhashi-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر ناظم الحاشي</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا روحي</h4>
                    <div class="poem-text text-gray-800">
                        يا روحي لا تحبين وتعبين،<br>
                        تراهم مو أهل وعد ولا يوفون.<br>
                        شگد ضحيت لأجلهم، ما دروا،<br>
                        تاليها تركوني وحيد بحزني.<br>
                        يا گلبي لا تلومني، ما بيدي،<br>
                        هي هاي الدنيا، يوم وياك ويوم عليك.<br>
                        عيش لنفسك، اترك الماضي،<br>
                        باچر يجي والكل ينسونك.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Raheem Al-Maliki Poems -->
    <section id="raheem-almaliki-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر رحيم المالكي</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">مشت روحي</h4>
                    <div class="poem-text text-gray-800">
                        مشت روحي وعفتها بيدك،<br>
                        عساني ما مشيت خطوة بلياك.<br>
                        كل درب أمشي، أحس خطواتي وياك،<br>
                        وكل دگة بگلبي تنادي باسمك.<br>
                        يا عيني لا تبچين بعد،<br>
                        ترا الدمع يخلص ويظل الجرح.<br>
                        أنا الما گدرت أعيش بلياك،<br>
                        روحي تطلع مني لو شفتك.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Abd Al-Hussein Al-Halfy Poems -->
    <section id="abd-alhussein-alhalfy-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر عبد الحسين الحلفي</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا گلبي</h4>
                    <div class="poem-text text-gray-800">
                        يا گلبي شبيك ما ترتاح؟<br>
                        من كثر الهموم والحزن.<br>
                        أنا اللي گضيت عمري حسرات،<br>
                        والفرح ما مر بيه ولا يوم.<br>
                        يا دنيتي كافي عذاب،<br>
                        روحي ملت من كثر الآهات.<br>
                        بس الصبر بگلبي ظل،<br>
                        أنتظر الفرج، يا رب.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Kareem Al-Iraqi Poems -->
    <section id="kareem-aliraqi-poems" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">قصائد الشاعر كريم العراقي</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا طيور الوداد</h4>
                    <div class="poem-text text-gray-800">
                        يا طيور الوداد، خذيني لحبيبي،<br>
                        گوليله روحي ذابت من الشوگ.<br>
                        عيوني ما نامت، تنتظر جيتك،<br>
                        گلبي ينادي باسمك، يا أملي.<br>
                        يا سنين العمر، ما تسوى بلياك،<br>
                        الفرح يختفي، والهم يزيد.<br>
                        أنا العاشق، أنا المتيم،<br>
                        حبي الك، يا حبيبي، ما يموت.
                    </div>
                </div>
            </div>
        </div>
    </section>


    <!-- Poetry Genre Specific Sections -->
    <!-- Love, Romantic Poetry List -->
    <section id="love-romantic-poetry-list" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر الحب والغزل والرومانسية</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- Poem 1: جبار رشيد - "يا أول عشگ" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا أول عشگ</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: جبار رشيد</p>
                    <div class="poem-text text-gray-800">
                        يا أول عشگ حنّيتله وعيني بكتله دموع،<br>
                        يا آخر نفس بضلوعي ظل بيّه يروح ويعود.<br>
                        شلون أنسى الليالي البيها چنت وياك؟<br>
                        شلون أطرد خيالك من يجي بجروحي؟<br>
                        روحي بيك تتوسّل، تعال ارجعلي.<br>
                        عمري بدونك ما يسوى ولا يوم.<br>
                        يا بعد كل ناسي وهلي، يا أغلى من الروح،<br>
                        لو تدري شگد أحبك، ما تبتعد عني.
                    </div>
                </div>
            </div>
            <!-- Poem 2: كاظم اسماعيل الكاطع - "مر بيه" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">مر بيه</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: كاظم اسماعيل الكاطع</p>
                    <div class="poem-text text-gray-800">
                        مر بيه يا هوى العشاگ من تمر،<br>
                        وخليلي شي من ريحة هدومك.<br>
                        أنا بلياك وردة وماتت من العطش،<br>
                        وبدونك عيني ما تشوف النوم.<br>
                        كل العمر يمشي وأنتظر ملكاك،<                        يا حلم السنين وكل دگة بگلبي.<br>
                        كون العمر يخلص وأنا بحضنك،<br>
                        لا أريد شي من الدنيا بس قربك.
                    </div>
                </div>
            </div>
            <!-- Poem 3: سمير صبيح - "وينك يل رحت" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-200">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">وينك يل رحت</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: سمير صبيح</p>
                    <div class="poem-text text-gray-800">
                        وينك يل رحت؟ وشوكي ظل بيك،<br>
                        كل درب مشيته أحس خطوة الك بيه.<br>
                        عيوني ما تمل النظر لو مر طيفك،<br>
                        وروحي تذوب حباً بيك.<br>
                        شلون أداري جرح گلبي بلياك؟<br>
                        وانت صرت الدوا والمرهم لجروحي.<br>
                        يا دنيا صرت بعيني بس طيف،<br>
                        لو ما شوكه ما أگدر أعيش لحظة.
                    </div>
                </div>
            </div>
             <!-- Poem 4: عريان السيد خلف - "كلشي منك حلو" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-300">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">كلشي منك حلو</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: عريان السيد خلف</p>
                    <div class="poem-text text-gray-800">
                        كلشي منك حلو، حتى عذابك يا حبيبي،<br>
                        تظل بگلبي شعلة نار ما تطفي.<br>
                        يا أول عشگ، يا آخر محبة،<br>
                        روحي وروحي ليك تروح.<br>
                        شگد حاولت أنساك، ما گدرت،<br>
                        صورك بالبال، ما تفارگ عيني.<br>
                        أنا العايش على ذكرى حبك،<br>
                        وبدونك، دنيتي ما تسوى شي.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Bold, Patriotic Poetry List -->
    <section id="bold-patriotic-poetry-list" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر جريء ووطني</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- Poem 1: مظفر النواب - "للريل وحمد" (مقتطف) -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">للريل وحمد (مقتطف)</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: مظفر النواب</p>
                    <div class="poem-text text-gray-800">
                        يا ريل صيح بقوة يا ريل،<br>
                        خلهم يسمعون الوجع بالريل.<br>
                        هاي الناس، هاي الوجوه التعبانة،<br>
                        منين اجوها هيچي ضيم وويل؟<br>
                        يا ريل، گص الروس العدلة،<br>
                        خل نخلص من هالذل والهوان،<br>
                        لا تعاتبني بعد، دمي يفور،<br>
                        أنا الثاير وما أقبل بالظلم.
                    </div>
                </div>
            </div>
            <!-- Poem 2: علي رشم - "دمي يحكي" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">دمي يحكي</h4>
                    <p class="text-lg text-gray-700 mb-4">للشهيد الشاعر: علي رشم</p>
                    <div class="poem-text text-gray-800">
                        دمي يحكي قصة وطن،<br>
                        بيها التضحية صارت فن.<br>
                        ما خفت من الموت لحظة،<br>
                        روحي فدوة لتراب الوطن.<br>
                        لو كل قطرة دم تصير شراع،<br>
                        أوصلك يا عراق لأعلى مكان.<br>
                        أنا ابنك يا دجلة والفرات،<br>
                        ترابك أغلى من الذهب، يا أغلى الأوطان.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Social & Wisdom Poetry List -->
    <section id="social-wisdom-poetry-list" class="container mx-auto py-16 px-6 md:px-12 hidden-section">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر اجتماعي وحكمة</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- Poem 1: عريان السيد خلف - "يا ديرتي" (مقتطف) -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا ديرتي (مقتطف)</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: عريان السيد خلف</p>
                    <div class="poem-text text-gray-800">
                        يا ديرتي الشالت هموم الناس،<br>
                        وجروحها ما طابت بيوم.<br>
                        كل بيت بيها قصة حزن،<br>
                        وكل روح بيها تشكي الظلوم.<br>
                        متى الفرح يجي لدروبها؟<                        وتنسى المر وتعيش بيوم.<br>
                        هاي الناس الطيبة الفقيرة،<br>
                        بس رب العباد يدري بظروفها.
                    </div>
                </div>
            </div>
             <!-- Poem 2: ناظم الحاشي - "يا روحي" -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl animation-delay-100">
                <div class="p-6">
                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">يا روحي</h4>
                    <p class="text-lg text-gray-700 mb-4">للشاعر: ناظم الحاشي</p>
                    <div class="poem-text text-gray-800">
                        يا روحي لا تحبين وتعبين،<br>
                        تراهم مو أهل وعد ولا يوفون.<br>
                        شگد ضحيت لأجلهم، ما دروا،<br>
                        تاليها تركوني وحيد بحزني.<br>
                        يا گلبي لا تلومني، ما بيدي،<                        هي هاي الدنيا، يوم وياك ويوم عليك.<br>
                        عيش لنفسك، اترك الماضي،<br>
                        باچر يجي والكل ينسونك.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Us Section -->
    <section id="contact-us" class="bg-orange-100 py-16 px-6 md:px-12 text-center rounded-lg shadow-inner mx-auto max-w-4xl fade-in-slide-rtl" style="background-color: #EEDC82; margin-top: 4rem; margin-bottom: 4rem;">
        <h2 class="text-4xl font-bold text-gray-800 mb-6">تواصل معنا</h2>
        <p class="text-xl text-gray-700 mb-8 max-w-2xl mx-auto">
            للاستفسارات، الاقتراحات، أو إضافة قصائد جديدة للموسوعة، يرجى ملء النموذج أدناه.
        </p>
        <form class="flex flex-col items-center gap-4 max-w-md mx-auto">
            <input type="text" placeholder="اسمك الكامل..." class="w-full p-4 rounded-full border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg">
            <input type="email" placeholder="بريدك الإلكتروني..." class="w-full p-4 rounded-full border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg">
            <textarea placeholder="رسالتك..." rows="5" class="w-full p-4 rounded-lg border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg"></textarea>
            <button type="submit" class="btn-primary bg-orange-500 text-white text-xl font-semibold py-4 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 w-full" aria-label="أرسل الرسالة">
                أرسل الرسالة
            </button>
        </form>
    </section>

    <!-- Footer Section -->
    <footer class="bg-gray-900 py-10 px-6 md:px-12 text-center text-gray-400">
        <div class="max-w-4xl mx-auto">
            <!-- About Us & Copyright -->
            <h2 class="text-3xl font-bold text-gray-200 mb-4">موسوعة الشعر الشعبي العراقي</h2>
            <p class="text-md text-gray-300 leading-relaxed mb-6">
                بوابتك الشاملة لأجمل القصائد والأبيات الشعرية لأبرز شعراء العراق العظام.<br>
                نسعى للحفاظ على هذا التراث الثقافي الغني وتقديمه لعشاق الشعر الأصيل.
                <br>
                © 2025 كرار حيدر. جميع الحقوق محفوظة.
            </p>

            <!-- Social Media Links with Icons -->
            <div class="flex justify-center space-x-6 space-x-reverse mb-6">
                <a href="https://www.instagram.com/k9x9i" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="Instagram">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="https://t.me/K1_ar1" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="Telegram">
                    <i class="fab fa-telegram-plane"></i>
                </a>
                <a href="https://www.youtube.com/@U1QO1" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="YouTube">
                    <i class="fab fa-youtube"></i>
                </a>
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="TikTok">
                    <i class="fab fa-tiktok"></i>
                </a>
            </div>

            <!-- Quick Links -->
            <div class="flex flex-wrap justify-center space-x-4 space-x-reverse text-sm footer-links">
                <a href="#" class="text-gray-400 hover:text-orange-400 transition duration-300">سياسة الخصوصية</a>
                <span class="text-gray-500 hidden md:inline">|</span>
                <a href="#" class="text-gray-400 hover:text-orange-400 transition duration-300">شروط الاستخدام</a>
                <span class="text-gray-500 hidden md:inline">|</span>
                <a href="#" class="text-gray-400 hover:text-orange-400 transition duration-300">خريطة الموقع</a>
            </div>
        </div>
    </footer>

    <script>
        // JavaScript for Header Show/Hide on Scroll
        let lastScrollY = window.scrollY;
        const header = document.getElementById('main-header');
        const headerOffsetTrigger = 200;

        header.classList.add('header-visible');

        window.addEventListener('scroll', function() {
            if (window.scrollY > lastScrollY && window.scrollY > headerOffsetTrigger) {
                header.classList.remove('header-visible');
                header.classList.add('header-hidden');
            } else if (window.scrollY < lastScrollY || window.scrollY <= headerOffsetTrigger) {
                header.classList.remove('header-hidden');
                header.classList.add('header-visible');
            }
            lastScrollY = window.scrollY;
        });

        // JavaScript for Scroll-Triggered Animations (Fade-in/Slide-in from right)
        document.addEventListener('DOMContentLoaded', function() {
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate-in');
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            document.querySelectorAll('.fade-in-slide-rtl').forEach(element => {
                observer.observe(element);
            });

            // Add lazy loading to images
            document.querySelectorAll('img').forEach(img => {
                img.setAttribute('loading', 'lazy');
            });

            // Handle navigation to sections and showing/hiding them
            const allSections = document.querySelectorAll('.container.mx-auto'); // All major content sections
            const poetSections = document.querySelectorAll('section[id$="-poems"]'); // Specific poet sections
            const genreSections = document.querySelectorAll('section[id$="-poetry-list"]'); // Specific genre sections
            const heroSection = document.getElementById('hero');
            const poetsDirectory = document.getElementById('poets-directory');
            const poetryGenres = document.getElementById('poetry-genres');

            function hideAllContentSections() {
                allSections.forEach(section => {
                    if (section.id !== 'hero' && section.id !== 'poets-directory' && section.id !== 'poetry-genres' && section.id !== 'contact-us') {
                        section.classList.add('hidden-section');
                    }
                });
            }

            function showSection(sectionId) {
                hideAllContentSections();
                const sectionToShow = document.getElementById(sectionId);
                if (sectionToShow) {
                    sectionToShow.classList.remove('hidden-section');
                    sectionToShow.scrollIntoView({ behavior: 'smooth' });
                }
            }

            // Initially hide all specific poet/genre sections
            poetSections.forEach(section => section.classList.add('hidden-section'));
            genreSections.forEach(section => section.classList.add('hidden-section'));

            // Navigation links click handlers
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function(event) {
                    event.preventDefault();
                    const targetId = this.getAttribute('href').substring(1); // Remove '#'
                    if (targetId === 'hero') {
                        // For home, show default sections and scroll to hero
                        poetSections.forEach(section => section.classList.add('hidden-section'));
                        genreSections.forEach(section => section.classList.add('hidden-section'));
                        heroSection.scrollIntoView({ behavior: 'smooth' });
                        poetsDirectory.classList.remove('hidden-section'); // Show poets directory
                        poetryGenres.classList.remove('hidden-section'); // Show poetry genres
                    } else if (targetId === 'poets-directory') {
                        // For poets directory, show only it initially
                        hideAllContentSections();
                        poetsDirectory.classList.remove('hidden-section');
                        poetsDirectory.scrollIntoView({ behavior: 'smooth' });
                    } else if (targetId === 'poetry-genres') {
                        // For poetry genres, show only it initially
                        hideAllContentSections();
                        poetryGenres.classList.remove('hidden-section');
                        poetryGenres.scrollIntoView({ behavior: 'smooth' });
                    } else if (targetId === 'contact-us') {
                        hideAllContentSections();
                        document.getElementById('contact-us').classList.remove('hidden-section');
                        document.getElementById('contact-us').scrollIntoView({ behavior: 'smooth' });
                    } else {
                        // For poet or genre specific links, show only that section
                        showSection(targetId);
                    }
                });
            });

            // Poet links click handlers
            document.querySelectorAll('.poet-entry a').forEach(link => {
                link.addEventListener('click', function(event) {
                    event.preventDefault();
                    const targetId = this.getAttribute('href').substring(1);
                    showSection(targetId);
                });
            });

            // Genre cards click handlers
            document.querySelectorAll('#poetry-genres a').forEach(link => {
                link.addEventListener('click', function(event) {
                    event.preventDefault();
                    const targetId = this.getAttribute('href').substring(1);
                    showSection(targetId);
                });
            });

            // Search functionality (client-side basic filtering)
            const searchInput = document.getElementById('searchInput');
            searchInput.addEventListener('keyup', function() {
                const searchTerm = searchInput.value.toLowerCase();
                const allPoetryCards = document.querySelectorAll('.poetry-card');
                const allPoetEntries = document.querySelectorAll('.poet-entry');

                // If search term is empty, show default sections
                if (searchTerm === '') {
                    hideAllContentSections(); // Hide all specific sections
                    heroSection.scrollIntoView({ behavior: 'smooth' }); // Scroll back to top
                    poetsDirectory.classList.remove('hidden-section'); // Show poets directory
                    poetryGenres.classList.remove('hidden-section'); // Show poetry genres
                } else {
                    // Hide all sections except for contact-us
                    allSections.forEach(section => {
                        if (section.id !== 'contact-us' && section.id !== 'hero') { // Keep hero for context
                            section.classList.add('hidden-section');
                        }
                    });

                    // Filter and show matching poetry cards (poems)
                    let foundPoem = false;
                    allPoetryCards.forEach(card => {
                        const poemText = card.querySelector('.poem-text')?.textContent.toLowerCase() || '';
                        const poemTitle = card.querySelector('h4')?.textContent.toLowerCase() || '';
                        const poetName = card.querySelector('p')?.textContent.toLowerCase() || ''; // Assuming poet name is in a <p> tag

                        if (poemText.includes(searchTerm) || poemTitle.includes(searchTerm) || poetName.includes(searchTerm)) {
                            card.closest('section').classList.remove('hidden-section'); // Show the section containing the poem
                            card.style.display = 'block'; // Show the card itself
                            foundPoem = true;
                        } else {
                            card.style.display = 'none'; // Hide non-matching cards
                        }
                    });

                    // Filter and show matching poet entries (poets)
                    let foundPoet = false;
                    allPoetEntries.forEach(poet => {
                        const poetName = poet.querySelector('p')?.textContent.toLowerCase() || '';
                        if (poetName.includes(searchTerm)) {
                            poetsDirectory.classList.remove('hidden-section'); // Show poets directory
                            poet.style.display = 'flex'; // Show the poet entry
                            foundPoet = true;
                        } else {
                            poet.style.display = 'none'; // Hide non-matching poet entries
                        }
                    });

                    // If no poem or poet found, consider adding a "no results" message
                    if (!foundPoem && !foundPoet && searchTerm !== '') {
                        // You might want to display a message like "لا توجد نتائج بحث"
                        // For simplicity, we'll just not show any poetry cards if nothing matches.
                    }
                }
            });

            // Adjust display for sections on initial load or navigation
            function adjustSectionVisibilityOnLoad() {
                // Hide all specific poet/genre sections initially
                poetSections.forEach(section => section.classList.add('hidden-section'));
                genreSections.forEach(section => section.classList.add('hidden-section'));
                document.getElementById('contact-us').classList.add('hidden-section'); // Hide contact us
                
                // Ensure poets directory and genres are visible by default on home
                poetsDirectory.classList.remove('hidden-section');
                poetryGenres.classList.remove('hidden-section');
            }
            adjustSectionVisibilityOnLoad(); // Call on initial load
        });
    </script>
</body>
</html>

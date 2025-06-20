<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أخبار الذكاء الاصطناعي</title>
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
            line-height: 1.6;
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

        /* Smooth slide-in animation for news articles */
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

        /* Read More button hover effect */
        .read-more-btn {
            overflow: hidden;
            position: relative;
            transition: color 0.3s ease-in-out;
            z-index: 1;
        }
        .read-more-btn::before {
            content: '';
            position: absolute;
            top: 0;
            right: 100%; /* For RTL, starts off to the right */
            width: 100%;
            height: 100%;
            background-color: #FFA500; /* Orange background on hover */
            transition: right 0.3s ease-in-out;
            z-index: -1;
            border-radius: 9999px; /* Match button's rounded shape */
        }
        .read-more-btn:hover::before {
            right: 0; /* Slides in from right */
        }
        .read-more-btn:hover {
            color: #FAF9F6; /* Text color changes to background color on hover */
        }

        /* Simple search input focus animation */
        .search-input:focus {
            border-color: #FFA500;
            box-shadow: 0 0 0 3px rgba(255, 165, 0, 0.2); /* Soft orange glow */
            outline: none;
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        /* Card hover effect for news articles */
        .news-card {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .news-card:hover {
            transform: translateY(-5px); /* Slight lift */
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.08); /* More pronounced shadow */
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
                    <!-- Logo Placeholder (Right aligned for RTL) -->
                    <div>
                        <a href="#" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            أخبار الذكاء الاصطناعي
                        </a>
                    </div>
                    <!-- Navigation Bar - Centered and side-by-side -->
                    <ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">
                        <li><a href="#hero" class="nav-link text-lg font-medium">الرئيسية</a></li>
                        <li><a href="#news-feed" class="nav-link text-lg font-medium">الأخبار</a></li>
                        <li><a href="#" class="nav-link text-lg font-medium">الذكاء الاصطناعي</a></li>
                        <li><a href="#" class="nav-link text-lg font-medium">التقنية</a></li>
                        <li><a href="#contact-us" class="nav-link text-lg font-medium">تواصل معنا</a></li>
                    </ul>
                </div>
                <!-- Search Bar - Large and Below Navigation Links -->
                <div class="relative w-full mt-4">
                    <input type="text" placeholder="ابحث عن أخبار ومقالات..." class="search-input w-full p-3 md:p-4 text-lg border border-gray-300 rounded-full focus:ring-0 text-right pr-12">
                    <button class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500 hover:text-orange-500 transition duration-300 text-xl" aria-label="بحث">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="relative h-screen flex items-center justify-center text-center bg-cover bg-center" style="background-color: #F4F1EE;">
        <div class="max-w-4xl px-4">
            <h1 class="text-6xl md:text-7xl font-extrabold text-gray-800 mb-6 leading-tight animate-fade-in">
                مرحبًا بك في <span class="text-orange-500">أخبار الذكاء الاصطناعي</span>
            </h1>
            <p class="text-2xl md:text-3xl text-gray-600 mb-10 animate-fade-in animation-delay-200">
                تغطية لأحدث تطورات التقنية حول العالم
            </p>
            <a href="#news-feed" class="btn-primary bg-orange-500 text-white text-xl md:text-2xl font-semibold py-4 px-10 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 animate-fade-in animation-delay-400">
                ابدأ التصفح
            </a>
        </div>
    </section>

    <!-- Featured Articles Section -->
    <section class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">مقالات مميزة</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Featured Article 1 -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                <img src="https://placehold.co/600x400/8B5E3C/FAF9F6?text=Featured+AI+1" alt="صورة مقال مميز 1" class="w-full h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    <h3 class="text-2xl font-semibold text-gray-800 mb-3">قفزة نوعية في التعلم العميق</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        أحدث الاختراقات في شبكات التعلم العميق التي تغير مفاهيم الذكاء الاصطناعي.
                    </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            </div>
            <!-- Featured Article 2 -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl animation-delay-100">
                <img src="https://placehold.co/600x400/EEDC82/8B5E3C?text=Featured+AI+2" alt="صورة مقال مميز 2" class="w-full h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    <h3 class="text-2xl font-semibold text-gray-800 mb-3">الذكاء الاصطناعي والأمن السيبراني</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        كيف يمكن للذكاء الاصطناعي تعزيز دفاعاتنا ضد التهديدات السيبرانية المتزايدة.
                    </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            </div>
            <!-- Featured Article 3 -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl animation-delay-200">
                <img src="https://placehold.co/600x400/FFA500/FAF9F6?text=Featured+AI+3" alt="صورة مقال مميز 3" class="w-full h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    <h3 class="text-2xl font-semibold text-gray-800 mb-3">مستقبل الروبوتات الذكية</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        تطورات مذهلة في عالم الروبوتات وتأثيرها على حياتنا اليومية والصناعة.
                    </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- News Feed Section -->
    <section id="news-feed" class="container mx-auto py-16 px-6 md:px-12 flex flex-col lg:flex-row gap-12">
        <!-- Main News Content -->
        <div class="lg:w-2/3">
            <h2 class="text-5xl font-bold text-gray-800 mb-12">أحدث الأخبار</h2>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Article 1 -->
                <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                    <img src="https://placehold.co/600x400/8B5E3C/FAF9F6?text=AI+Image+1" alt="صورة مقال 1" class="w-full h-56 object-cover rounded-t-lg">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">ثورة الذكاء الاصطناعي في الرعاية الصحية</h3>
                        <p class="text-gray-600 mb-4 text-sm">
                            يُحدث الذكاء الاصطناعي تحولاً جذرياً في قطاع الرعاية الصحية، من التشخيص الدقيق إلى تطوير الأدوية الجديدة.
                        </p>
                        <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                            قراءة المزيد
                        </button>
                    </div>
                </div>

                <!-- Article 2 -->
                <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                    <img src="https://placehold.co/600x400/EEDC82/8B5E3C?text=AI+Image+2" alt="صورة مقال 2" class="w-full h-56 object-cover rounded-t-lg">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">مستقبل العمل والذكاء الاصطناعي التوليدي</h3>
                        <p class="text-gray-600 mb-4 text-sm">
                            كيف سيعيد الذكاء الاصطناعي التوليدي تشكيل سوق العمل والوظائف في العقد القادم؟ تحليل شامل.
                        </p>
                        <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                            قراءة المزيد
                        </button>
                    </div>
                </div>

                <!-- Article 3 -->
                <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                    <img src="https://placehold.co/600x400/FFA500/FAF9F6?text=AI+Image+3" alt="صورة مقال 3" class="w-full h-56 object-cover rounded-t-lg">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">التحديات الأخلاقية للذكاء الاصطناعي</h3>
                        <p class="text-gray-600 mb-4 text-sm">
                            مناقشة للتحديات الأخلاقية والقانونية التي يطرحها التطور السريع لأنظمة الذكاء الاصطناعي.
                        </p>
                        <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                            قراءة المزيد
                        </button>
                    </div>
                </div>

                <!-- Article 4 -->
                <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                    <img src="https://placehold.co/600x400/8B5E3C/EEDC82?text=AI+Image+4" alt="صورة مقال 4" class="w-full h-56 object-cover rounded-t-lg">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">الذكاء الاصطناعي في الفضاء والاستكشاف</h3>
                        <p class="text-gray-600 mb-4 text-sm">
                            كيف يساهم الذكاء الاصطناعي في مهمات استكشاف الفضاء واكتشاف الكواكب الجديدة.
                        </p>
                        <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                            قراءة المزيد
                        </button>
                    </div>
                </div>
            </div>

            <!-- Load More Button -->
            <div class="text-center mt-12 fade-in-slide-rtl">
                <button class="btn-primary bg-orange-500 text-white text-xl font-semibold py-3 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300">
                    تحميل المزيد من الأخبار
                </button>
            </div>
        </div>

        <!-- Sidebar Section -->
        <aside class="lg:w-1/3">
            <div class="bg-white rounded-lg shadow-md p-6 mb-8 fade-in-slide-rtl">
                <h3 class="text-2xl font-semibold text-gray-800 mb-6">مواضيع مقترحة</h3>
                <ul class="space-y-3 mb-8 text-lg">
                    <li><a href="#" class="text-gray-700 hover:text-orange-500 transition duration-300">#الذكاء_الاصطناعي_الأخلاقي</a></li>
                    <li><a href="#" class="text-gray-700 hover:text-orange-500 transition duration-300">#التعلم_العميق</a></li>
                    <li><a href="#" class="text-gray-700 hover:text-orange-500 transition duration-300">#روبوتات_المستقبل</a></li>
                    <li><a href="#" class="text-gray-700 hover:text-orange-500 transition duration-300">#السيارات_ذاتية_القيادة</a></li>
                    <li><a href="#" class="text-gray-700 hover:text-orange-500 transition duration-300">#الابتكار_التقني</a></li>
                </ul>
            </div>

            <div class="bg-white rounded-lg shadow-md p-6 mb-8 fade-in-slide-rtl">
                <h3 class="text-2xl font-semibold text-gray-800 mb-6">أحدث المقالات</h3>
                <ul class="space-y-4 text-lg">
                    <li>
                        <a href="#" class="block text-gray-700 hover:text-orange-500 transition duration-300">
                            <p class="font-medium">تأثير الذكاء الاصطناعي على صناعة المحتوى</p>
                            <span class="text-sm text-gray-500">منذ 3 ساعات</span>
                        </a>
                    </li>
                    <li>
                        <a href="#" class="block text-gray-700 hover:text-orange-500 transition duration-300">
                            <p class="font-medium">تطورات تقنية في معالجة اللغات الطبيعية</p>
                            <span class="text-sm text-gray-500">منذ يوم واحد</span>
                        </a>
                    </li>
                    <li>
                        <a href="#" class="block text-gray-700 hover:text-orange-500 transition duration-300">
                            <p class="font-medium">الذكاء الاصطناعي في الفن والإبداع</p>
                            <span class="text-sm text-gray-500">منذ يومين</span>
                        </a>
                    </li>
                </ul>
            </div>

            <div class="bg-white rounded-lg shadow-md p-6 fade-in-slide-rtl">
                <h3 class="text-2xl font-semibold text-gray-800 mb-6">تابعنا</h3>
                <div class="flex justify-center space-x-6 space-x-reverse">
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-3xl" aria-label="Telegram">
                        <i class="fab fa-telegram-plane"></i>
                    </a>
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-3xl" aria-label="Instagram">
                        <i class="fab fa-instagram"></i>
                    </a>
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-3xl" aria-label="YouTube">
                        <i class="fab fa-youtube"></i>
                    </a>
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-3xl" aria-label="Twitter">
                        <i class="fab fa-twitter"></i>
                    </a>
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-3xl" aria-label="LinkedIn">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                </div>
            </div>
        </aside>
    </section>

    <!-- Newsletter Subscription Section -->
    <section class="bg-orange-100 py-16 px-6 md:px-12 text-center rounded-lg shadow-inner mx-auto max-w-4xl fade-in-slide-rtl" style="background-color: #EEDC82; margin-top: 4rem; margin-bottom: 4rem;">
        <h2 class="text-4xl font-bold text-gray-800 mb-6">اشترك في نشرتنا الإخبارية</h2>
        <p class="text-xl text-gray-700 mb-8 max-w-2xl mx-auto">
            احصل على أحدث الأخبار والمقالات حول الذكاء الاصطناعي مباشرة في صندوق بريدك الوارد.
        </p>
        <div class="flex flex-col md:flex-row justify-center items-center gap-4">
            <input type="email" placeholder="أدخل بريدك الإلكتروني..." class="w-full md:w-1/2 p-4 rounded-full border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg">
            <button class="btn-primary bg-orange-500 text-white text-xl font-semibold py-4 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 w-full md:w-auto" aria-label="اشترك الآن">
                اشترك الآن
            </button>
        </div>
    </section>

    <!-- About Us Section -->
    <section id="about-us" class="container mx-auto py-16 px-6 md:px-12 text-center fade-in-slide-rtl">
        <h2 class="text-5xl font-bold text-gray-800 mb-12">عن أخبار الذكاء الاصطناعي</h2>
        <p class="text-lg md:text-xl text-gray-700 leading-relaxed max-w-3xl mx-auto">
            "أخبار الذكاء الاصطناعي" هي بوابتك الشاملة لأحدث التطورات والابتكارات في عالم الذكاء الاصطناعي والتقنية. نسعى لتقديم محتوى دقيق وموثوق، وتحليلات عميقة، وتقارير حصرية لمساعدتك على فهم المشهد المتغير باستمرار للذكاء الاصطناعي وتأثيره على مستقبلنا. مهمتنا هي إلهام المعرفة والابتكار في المجتمع العربي.
        </p>
    </section>

    <!-- Footer Section -->
    <footer class="bg-gray-100 py-10 px-6 md:px-12 text-center text-gray-600 rounded-t-lg shadow-inner">
        <div class="mb-6">
            <p class="text-xl font-semibold text-gray-800 mb-2">أخبار الذكاء الاصطناعي</p>
            <p class="text-md text-gray-700 max-w-lg mx-auto">
                بوابتك الموثوقة لآخر أخبار وتطورات الذكاء الاصطناعي والتقنية حول العالم.
            </p>
        </div>

        <div class="flex justify-center space-x-6 space-x-reverse mb-6">
            <!-- Social Media Icons (using Font Awesome) -->
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-2xl" aria-label="Telegram">
                <i class="fab fa-telegram-plane"></i>
            </a>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-2xl" aria-label="Instagram">
                <i class="fab fa-instagram"></i>
            </a>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-2xl" aria-label="YouTube">
                <i class="fab fa-youtube"></i>
            </a>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-2xl" aria-label="Twitter">
                <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300 text-2xl" aria-label="LinkedIn">
                <i class="fab fa-linkedin-in"></i>
            </a>
        </div>

        <div class="mb-4 text-lg">
            <p>© 2025 كرار حيدر. جميع الحقوق محفوظة.</p>
        </div>
        <div class="flex flex-wrap justify-center space-x-4 space-x-reverse text-sm">
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300">سياسة الخصوصية</a>
            <span class="text-gray-400">|</span>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300">شروط الاستخدام</a>
            <span class="text-gray-400">|</span>
            <a href="#" class="text-gray-600 hover:text-orange-500 transition duration-300">خريطة الموقع</a>
        </div>
    </footer>

    <script>
        // JavaScript for Header Show/Hide on Scroll with "Frame" Positioning
        let lastScrollY = window.scrollY;
        const header = document.getElementById('main-header');
        const headerHeight = header.offsetHeight; // Get the initial height of the header

        // Set initial header position
        header.classList.add('header-visible'); // Ensure it's visible on load

        window.addEventListener('scroll', function() {
            if (window.scrollY > lastScrollY && window.scrollY > headerHeight) {
                // Scrolling down and past the header's height
                header.classList.remove('header-visible');
                header.classList.add('header-hidden');
            } else if (window.scrollY < lastScrollY) {
                // Scrolling up
                header.classList.remove('header-hidden');
                header.classList.add('header-visible');
            }
            lastScrollY = window.scrollY;
        });

        // JavaScript for Scroll-Triggered Animations (Fade-in/Slide-in from right)
        document.addEventListener('DOMContentLoaded', function() {
            const observerOptions = {
                root: null, // relative to the viewport
                rootMargin: '0px',
                threshold: 0.1 // Trigger when 10% of the element is visible
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate-in');
                        observer.unobserve(entry.target); // Stop observing once animated
                    }
                });
            }, observerOptions);

            // Observe all elements with the 'fade-in-slide-rtl' class
            document.querySelectorAll('.fade-in-slide-rtl').forEach(element => {
                observer.observe(element);
            });
        });
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أخبار الذكاء الاصطناعي</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" xintegrity="sha512-R4R/Y8A+Kz/q3F+G9+Y8zF1+W+g7/Q/n6Gz+g/Y7+W8/W9+N7/X6+T7/G6+Z9+F8/V7/T6/F5/R4/V3/T2/G1/Z0/A9/B8/C7/D6/E5/F4/I3/J2/K1/L0/M9/N8/O7/P6/Q5/R4/S3/T2/U1/V0/W9/X8/Y7/Z6/a5/b4/c3/d2" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        /* Global Styles */
        body {
            [span_0](start_span)font-family: 'Tajawal', sans-serif;[span_0](end_span)
            [span_1](start_span)background-color: #FAF9F6;[span_1](end_span)
            /* Light beige/off-white background */
            [span_2](start_span)color: #333;[span_2](end_span)
            /* Soft dark grey for general text */
            [span_3](start_span)line-height: 1.6;[span_3](end_span)
            scroll-behavior: smooth; /* Smooth scrolling for anchor links */
        }

        /* Utility for delaying animations */
        [span_4](start_span).animation-delay-100 { animation-delay: 0.1s;[span_4](end_span)
        }
        [span_5](start_span).animation-delay-200 { animation-delay: 0.2s;[span_5](end_span)
        }
        [span_6](start_span).animation-delay-300 { animation-delay: 0.3s;[span_6](end_span)
        }
        [span_7](start_span).animation-delay-400 { animation-delay: 0.4s;[span_7](end_span)
        }

        /* Keyframe for simple fade-in (used for hero text) */
        @keyframes fadeIn {
            [span_8](start_span)from { opacity: 0;[span_8](end_span)
            transform: translateY(20px); }
            [span_9](start_span)to { opacity: 1; transform: translateY(0);[span_9](end_span)
            }
        }
        .animate-fade-in {
            [span_10](start_span)animation: fadeIn 0.8s ease-out forwards;[span_10](end_span)
            opacity: 0; /* Hidden by default */
        }

        /* Header Frame Styling */
        .header-frame {
            [span_11](start_span)background-color: #F4F1EE;[span_11](end_span)
            /* Slightly darker background for the frame */
            [span_12](start_span)border-radius: 1rem;[span_12](end_span)
            /* Rounded corners for the frame */
            [span_13](start_span)padding: 1.25rem 2.5rem;[span_13](end_span)
            /* More padding for a distinct frame */
            [span_14](start_span)box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);[span_14](end_span)
            /* Soft shadow for depth */
            [span_15](start_span)max-width: 90%;[span_15](end_span)
            /* Max width for the frame */
            [span_16](start_span)margin: 0 auto;[span_16](end_span)
            /* Center the frame */
        }

        /* Header Show/Hide Animation */
        #main-header {
            [span_17](start_span)transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;[span_17](end_span)
        }
        .header-hidden {
            [span_18](start_span)transform: translateY(-150%);[span_18](end_span)
            /* Move further up to completely hide */
            [span_19](start_span)opacity: 0;[span_19](end_span)
        }
        .header-visible {
            [span_20](start_span)transform: translateY(0);[span_20](end_span)
            opacity: 1;
        }

        /* Smooth slide-in animation for news articles */
        .fade-in-slide-rtl {
            [span_21](start_span)opacity: 0;[span_21](end_span)
            transform: translateX(20px); /* Start slightly to the right */
            [span_22](start_span)transition: opacity 0.6s ease-out, transform 0.6s ease-out;[span_22](end_span)
        }
        .fade-in-slide-rtl.animate-in {
            [span_23](start_span)opacity: 1;[span_23](end_span)
            transform: translateX(0); /* Slide to original position */
        }

        /* Hover effects for navigation links */
        .nav-link {
            [span_24](start_span)position: relative;[span_24](end_span)
            color: #8B5E3C; /* Walnut brown for links */
            [span_25](start_span)transition: color 0.3s ease-in-out;[span_25](end_span)
            z-index: 1;
        }
        .nav-link:hover {
            [span_26](start_span)color: #FFA500;[span_26](end_span)
            /* Warm orange on hover */
        }
        .nav-link::after {
            [span_27](start_span)content: '';[span_27](end_span)
            display: block;
            width: 0;
            height: 2px;
            background: #FFA500;
            transition: width 0.3s ease-out;
            position: absolute;
            bottom: -5px;
            [span_28](start_span)right: 0;[span_28](end_span)
            /* For RTL */
        }
        .nav-link:hover::after {
            [span_29](start_span)width: 100%;[span_29](end_span)
            left: 0; /* For RTL */
        }

        /* Button hover effect */
        .btn-primary {
            [span_30](start_span)transition: background-color 0.3s ease-in-out, transform 0.2s ease-in-out, box-shadow 0.3s ease-in-out;[span_30](end_span)
        }
        .btn-primary:hover {
            [span_31](start_span)background-color: #EEDC82;[span_31](end_span)
            /* Muted yellow on hover */
            [span_32](start_span)transform: translateY(-2px);[span_32](end_span)
            /* Slight lift */
            [span_33](start_span)box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);[span_33](end_span)
            /* Soft shadow on hover */
        }

        /* Read More button hover effect */
        .read-more-btn {
            [span_34](start_span)overflow: hidden;[span_34](end_span)
            position: relative;
            transition: color 0.3s ease-in-out;
            z-index: 1;
        }
        .read-more-btn::before {
            [span_35](start_span)content: '';[span_35](end_span)
            position: absolute;
            top: 0;
            right: 100%; /* For RTL, starts off to the right */
            [span_36](start_span)width: 100%;[span_36](end_span)
            height: 100%;
            background-color: #FFA500; /* Orange background on hover */
            [span_37](start_span)transition: right 0.3s ease-in-out;[span_37](end_span)
            z-index: -1;
            border-radius: 9999px; /* Match button's rounded shape */
        }
        .read-more-btn:hover::before {
            [span_38](start_span)right: 0;[span_38](end_span)
            /* Slides in from right */
        }
        .read-more-btn:hover {
            [span_39](start_span)color: #FAF9F6;[span_39](end_span)
            /* Text color changes to background color on hover */
        }

        /* Simple search input focus animation */
        .search-input:focus {
            [span_40](start_span)border-color: #FFA500;[span_40](end_span)
            box-shadow: 0 0 0 3px rgba(255, 165, 0, 0.2); /* Soft orange glow */
            [span_41](start_span)outline: none;[span_41](end_span)
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        /* Card hover effect for news articles */
        .news-card {
            [span_42](start_span)transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;[span_42](end_span)
        }
        .news-card:hover {
            [span_43](start_span)transform: translateY(-5px);[span_43](end_span)
            /* Slight lift */
            [span_44](start_span)box-shadow: 0 10px 20px rgba(0, 0, 0, 0.08);[span_44](end_span)
            /* More pronounced shadow */
        }

        /* Adjustments for Hero Section padding */
        #hero {
            [span_45](start_span)padding-top: 10rem;[span_45](end_span)
            /* Adjusted for smaller screens / to move content down */
            [span_46](start_span)min-height: 100vh;[span_46](end_span)
            /* Ensure it takes full viewport height */
            [span_47](start_span)display: flex;[span_47](end_span)
            align-items: center;
            justify-content: center;
        }

        /* Responsive adjustments for mobile and tablet */
        @media (max-width: 768px) {
            .header-frame {
                [span_48](start_span)padding: 1rem;[span_48](end_span)
                /* Smaller padding on mobile */
                [span_49](start_span)max-width: 95%;[span_49](end_span)
                /* Wider on mobile */
            }
            .header-frame .flex-col {
                [span_50](start_span)flex-direction: column;[span_50](end_span)
            }
            .header-frame .md\:flex-row {
                [span_51](start_span)flex-direction: column;[span_51](end_span)
                align-items: center;
            }
            .header-frame .md\:space-x-6 {
                [span_52](start_span)margin-top: 1rem;[span_52](end_span)
                justify-content: center;
            }
            .header-frame .text-3xl {
                [span_53](start_span)font-size: 1.75rem;[span_53](end_span)
                /* Smaller logo text on mobile */
            }
            .nav-link {
                [span_54](start_span)font-size: 1rem;[span_54](end_span)
                /* Smaller nav links on mobile */
            }
            .search-input {
                [span_55](start_span)padding: 0.75rem;[span_55](end_span)
                /* Smaller search input padding */
                [span_56](start_span)font-size: 1rem;[span_56](end_span)
                /* Smaller search input text */
            }
            #hero h1 {
                [span_57](start_span)font-size: 3rem;[span_57](end_span)
                /* Smaller hero title on mobile */
            }
            #hero p {
                [span_58](start_span)font-size: 1.25rem;[span_58](end_span)
                /* Smaller hero subtitle on mobile */
            }
            .btn-primary {
                [span_59](start_span)font-size: 1.1rem;[span_59](end_span)
                /* Smaller button text on mobile */
                [span_60](start_span)padding: 0.75rem 2rem;[span_60](end_span)
                /* Smaller button padding */
            }
            .news-card .p-6 {
                [span_61](start_span)padding: 1rem;[span_61](end_span)
                /* Smaller card padding on mobile */
            }
            .news-card h3 {
                [span_62](start_span)font-size: 1.5rem;[span_62](end_span)
                /* Smaller card title on mobile */
            }
            .text-5xl { /* Section titles */
                [span_63](start_span)font-size: 2.5rem;[span_63](end_span)
            }
            .text-4xl { /* Newsletter title */
                [span_64](start_span)font-size: 2rem;[span_64](end_span)
            }
            .text-xl { /* Newsletter subtitle */
                [span_65](start_span)font-size: 1rem;[span_65](end_span)
            }
            .footer-links {
                [span_66](start_span)flex-direction: column;[span_66](end_span)
                gap: 0.5rem;
            }
        }

        /* Adjustments for tablets (iPad) */
        @media (min-width: 769px) and (max-width: 1024px) {
            .header-frame {
                [span_67](start_span)padding: 1.5rem 3rem;[span_67](end_span)
            }
            #hero h1 {
                [span_68](start_span)font-size: 4.5rem;[span_68](end_span)
            }
            #hero p {
                [span_69](start_span)font-size: 2rem;[span_69](end_span)
            }
            .news-card h3 {
                [span_70](start_span)font-size: 1.75rem;[span_70](end_span)
            }
            .text-5xl {
                [span_71](start_span)font-size: 3.5rem;[span_71](end_span)
            }
            .text-4xl {
                [span_72](start_span)font-size: 2.5rem;[span_72](end_span)
            }
            .text-xl {
                [span_73](start_span)font-size: 1.15rem;[span_73](end_span)
            }
        }
    </style>
</head>
<body>

    <header id="main-header" class="fixed top-4 left-1/2 -translate-x-1/2 w-full z-50 transition-all duration-300 ease-in-out header-visible">
        <div class="header-frame">
            <nav class="flex flex-col items-center">
                [span_74](start_span)<div class="flex flex-col md:flex-row[span_74](end_span) justify-between items-center w-full mb-4 md:mb-0">
                    <div>
                        <a href="#" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            أخبار الذكاء الاصطناعي
                        </a>
                    </div>
                    [span_75](start_span)<ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">[span_75](end_span)
                        <li><a href="#hero" class="nav-link text-lg font-medium">الرئيسية</a></li>
                        <li><a href="#news-feed" class="nav-link text-lg font-medium">الأخبار</a></li>
                        <li><a href="#news-feed" class="nav-link text-lg font-medium">الذكاء الاصطناعي</a></li>
                        [span_76](start_span)<li><a href="#news-feed" class="nav-link text-lg font-medium">التقنية</a></li>[span_76](end_span)
                        <li><a href="#newsletter-subscription" class="nav-link text-lg font-medium">تواصل معنا</a></li>
                    </ul>
                </div>
                [span_77](start_span)<div class="relative w-full mt-4">[span_77](end_span)
                    <input type="text" placeholder="ابحث عن أخبار ومقالات..." class="search-input w-full p-3 md:p-4 text-lg border border-gray-300 rounded-full focus:ring-0 text-right pr-12">
                    [span_78](start_span)<button class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500 hover:text-orange-500 transition duration-300[span_78](end_span) text-xl" aria-label="بحث">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </nav>
        </div>
    </header>

    [span_79](start_span)<section id="hero" class="relative bg-cover bg-center text-center flex flex-col items-center justify-center" style="background-color: #F4F1EE;">[span_79](end_span)
        <div class="max-w-4xl px-4 py-20"> <h1 class="text-6xl md:text-7xl font-extrabold text-gray-800 mb-6 leading-tight animate-fade-in">
                مرحبًا بك في <span class="text-orange-500">أخبار الذكاء الاصطناعي</span>
            </h1>
            <p class="text-2xl md:text-3xl text-gray-600 mb-10 animate-fade-in animation-delay-200">
                [span_80](start_span)تغطية لأحدث تطورات التقنية حول العالم[span_80](end_span)
            </p>
            <a href="#news-feed" class="btn-primary bg-orange-500 text-white text-xl md:text-2xl font-semibold py-4 px-10 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 animate-fade-in animation-delay-400">
                ابدأ التصفح
            </a>
        </div>
    </section>

    [span_81](start_span)
    <section class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">مقالات مميزة</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl">
                <img src="https://placehold.co/600x400/8B5E3C/FAF9F6?text=Featured+AI+1" alt="صورة مقال مميز 1" class="w-full[span_81](end_span) h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    <h3 class="text-2xl font-semibold text-gray-800 mb-3">قفزة نوعية في التعلم العميق</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        [span_82](start_span)أحدث الاختراقات في شبكات التعلم العميق[span_82](end_span) التي تغير مفاهيم الذكاء الاصطناعي.
                    </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            [span_83](start_span)</div>[span_83](end_span)
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl animation-delay-100">
                <img src="https://placehold.co/600x400/EEDC82/8B5E3C?text=Featured+AI+2" alt="صورة مقال مميز 2" class="w-full h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    [span_84](start_span)<h3[span_84](end_span) class="text-2xl font-semibold text-gray-800 mb-3">الذكاء الاصطناعي والأمن السيبراني</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        [span_85](start_span)كيف يمكن للذكاء الاصطناعي تعزيز دفاعاتنا ضد التهديدات السيبرانية المتزايدة.[span_85](end_span) </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            [span_86](start_span)</div>[span_86](end_span)
            <div class="bg-white rounded-lg shadow-md overflow-hidden news-card fade-in-slide-rtl animation-delay-200">
                <img src="https://placehold.co/600x400/FFA500/FAF9F6?text=Featured+AI+3" alt="صورة مقال مميز 3" class="w-full h-56 object-cover rounded-t-lg">
                <div class="p-6">
                    [span_87](start_span)<h3[span_87](end_span) class="text-2xl font-semibold text-gray-800 mb-3">مستقبل الروبوتات الذكية</h3>
                    <p class="text-gray-600 mb-4 text-sm">
                        [span_88](start_span)تطورات مذهلة في عالم الروبوتات وتأثيرها على حياتنا اليومية والصناعة.[span_88](end_span) </p>
                    <button class="read-more-btn relative inline-block py-2 px-4 text-orange-500 border border-orange-500 rounded-full text-md font-medium focus:outline-none">
                        قراءة المزيد
                    </button>
                </div>
            [span_89](start_span)</div>[span_89](end_span)
        </div>
    </section>

    <section id="news-feed" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 mb-12">أحدث الأخبار</h2>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8"> <script type="text/javascript" src="https://feed.mikle.com/js/fw-loader.js" preloader-text="Loading" data-fw-param="173651/"></script>
            </div>

        [span_90](start_span)<div class="text-center mt-12 fade-in-slide-rtl">[span_90](end_span)
            <button class="btn-primary bg-orange-500 text-white text-xl font-semibold py-3 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300">
                تحميل المزيد من الأخبار
            </button>
        [span_91](start_span)</div>[span_91](end_span)
    </section>

    <section id="newsletter-subscription" class="bg-orange-100 py-16 px-6 md:px-12 text-center rounded-lg shadow-inner mx-auto max-w-4xl fade-in-slide-rtl" style="background-color: #EEDC82; margin-top: 4rem; margin-bottom: 4rem;">
        <h2 class="text-4xl font-bold text-gray-800 mb-6">اشترك في نشرتنا الإخبارية</h2>
        <p class="text-xl text-gray-700 mb-8 max-w-2xl mx-auto">
            [span_92](start_span)احصل على أحدث الأخبار والمقالات حول الذكاء الاصطناعي مباشرة في صندوق بريدك الوارد.[span_92](end_span) </p>
        <div class="flex flex-col md:flex-row justify-center items-center gap-4">
            <input type="email" placeholder="أدخل بريدك الإلكتروني..." class="w-full md:w-1/2 p-4 rounded-full border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg">
            <button class="btn-primary bg-orange-500 text-white text-xl font-semibold py-4 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 w-full md:w-auto" aria-label="اشترك الآن">
                اشترك الآن
            </button>
        [span_93](start_span)</div>[span_93](end_span)
    </section>

    <footer class="bg-gray-900 py-10 px-6 md:px-12 text-center text-gray-400">
        <div class="max-w-4xl mx-auto">
            <h2 class="text-3xl font-bold text-gray-200 mb-4">أخبار الذكاء الاصطناعي</h2>
            <p class="text-md text-gray-300 leading-relaxed mb-6">
                [span_94](start_span)بوابتك الشاملة لآخر التطورات والابتكارات في عالم الذكاء الاصطناعي والتقنية.[span_94](end_span) [span_95](start_span)نسعى لتقديم محتوى دقيق وموثوق، وتحليلات عميقة لإلهام المعرفة والابتكار في المجتمع العربي.[span_95](end_span) <br>
                [span_96](start_span)© 2025 كرار حيدر.[span_96](end_span) [span_97](start_span)جميع الحقوق محفوظة.[span_97](end_span)
            </p>

            <div class="flex justify-center space-x-6 space-x-reverse mb-6">
                <a href="https://www.instagram.com/k9x9i" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="Instagram">
                    <i class="fab fa-instagram"></i>
                [span_98](start_span)</a>[span_98](end_span)
                <a href="https://t.me/K1_ar1" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="Telegram">
                    <i class="fab fa-telegram-plane"></i>
                </a>
                <a href="https://www.youtube.com/@U1QO1" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="YouTube">
                    <i class="fab fa-youtube"></i>
                [span_99](start_span)</a>[span_99](end_span)
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="TikTok">
                    <i class="fab fa-tiktok"></i>
                </a>
            [span_100](start_span)</div>[span_100](end_span)

            <div class="flex flex-wrap justify-center space-x-4 space-x-reverse text-sm footer-links">
                <a href="#" class="text-gray-400 hover:text-orange-400 transition duration-300">سياسة الخصوصية</a>
                <span class="text-gray-500 hidden md:inline">|</span>
                [span_101](start_span)<a href="#" class="text-gray-400[span_101](end_span) hover:text-orange-400 transition duration-300">شروط الاستخدام</a>
                <span class="text-gray-500 hidden md:inline">|</span>
                <a href="#" class="text-gray-400 hover:text-orange-400 transition duration-300">خريطة الموقع</a>
            </div>
        </div>
    </footer>

    <script>
        // JavaScript for Header Show/Hide on Scroll with "Frame" Positioning
        [span_102](start_span)let lastScrollY =[span_102](end_span) window.scrollY;
        const header = document.getElementById('main-header');
        const headerOffsetTrigger = 200; // Distance to scroll down before hiding header

        // Ensure header is visible on page load
        [span_103](start_span)header.classList.add('header-visible');[span_103](end_span)
        window.addEventListener('scroll', function() {
            if (window.scrollY > lastScrollY && window.scrollY > headerOffsetTrigger) {
                // Scrolling down and past the trigger point
                header.classList.remove('header-visible');
                header.classList.add('header-hidden');
            } else if (window.scrollY < lastScrollY || window.scrollY <= headerOffsetTrigger) {
                [span_104](start_span)// Scrolling up or near the top[span_104](end_span)
                header.classList.remove('header-hidden');
                header.classList.add('header-visible');
            }
            lastScrollY = window.scrollY;
        });
        [span_105](start_span)// JavaScript for Scroll-Triggered Animations (Fade-in/Slide-in from right)[span_105](end_span)
        document.addEventListener('DOMContentLoaded', function() {
            const observerOptions = {
                root: null, // relative to the viewport
                rootMargin: '0px',
                threshold: 0.1 // Trigger when 10% of the element is visible
            [span_106](start_span)};[span_106](end_span)

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate-in');
                        [span_107](start_span)observer.unobserve(entry.target); // Stop observing once animated[span_107](end_span)
                    }
                });
            }, observerOptions);

            // Observe all elements with the 'fade-in-slide-rtl' class
            [span_108](start_span)document.querySelectorAll('.fade-in-slide-rtl').forEach(element => {[span_108](end_span)
                observer.observe(element);
            });
        [span_109](start_span)});[span_109](end_span)
    </script>
</body>
</html>

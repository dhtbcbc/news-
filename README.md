<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر الشعبي العراقي</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" integrity="sha512-R4R/Y8A+Kz/q3F+G9+Y8zF1+W+g7/Q/n6Gz+g/Y7+W8/W9+N7/X6+T7/G6+Z9+F8/V7/T6/F5/R4/V3/T2/G1/Z0/A9/B8/C7/D6/E5/F4/I3/J2/K1/L0/M9/N8/O7/P6/Q5/R4/S3/T2/U1/V0/W9/X8/Y7/Z6/a5/b4/c3/d2/e1/f0/g9/h8/i7/j6/k5/l4/m3/n2/o1/p0/q9/r8/s7/t6/u5/v4/w3/x2/y1/z0/A9/B8/C7/D6/E5/F4/G3/H2/I1/J0/K9/L8/M7/N6/O5/P4/Q3/R2/S1/T0/U9/V8/W7/X6/Y5/Z4/a3/b2/c1/d0/e9/f8/g7/h6/i5/j4/k3/l2/m1/n0/o9/p8/q7/r6/s5/t4/u3/v2/w3/x2/y1/z0" crossorigin="anonymous" referrerpolicy="no-referrer" />
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
        .poetry-card, .poet-entry, .genre-entry {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .poetry-card:hover, .poet-entry:hover, .genre-entry:hover {
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

        /* Poet entry styling (card with name) */
        .poet-entry, .genre-entry {
            background-color: #FFF;
            border-radius: 0.75rem; /* Slightly more rounded */
            padding: 1.5rem; /* More padding */
            text-align: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.06); /* Softer shadow */
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100%; /* Ensure consistent height in grid */
            cursor: pointer; /* Indicate clickable */
            border: 2px solid transparent; /* Default transparent border */
        }
        .poet-entry:hover, .genre-entry:hover {
            border-color: #FFA500; /* Orange border on hover */
        }

        .poet-entry h3, .genre-entry h3 {
            font-size: 1.5rem; /* Larger font for names */
            font-weight: 700;
            color: #333;
            margin-bottom: 0; /* No margin at bottom */
        }

        /* Hidden Section for SPA approach */
        .hidden-section {
            display: none !important;
        }

        /* Back Button Style */
        .back-button {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background-color: #8B5E3C; /* Darker brown */
            color: white;
            padding: 0.75rem 1.5rem;
            border-radius: 0.75rem;
            font-weight: 600;
            transition: background-color 0.3s ease, transform 0.2s ease;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        .back-button:hover {
            background-color: #6A4B2E; /* Even darker brown */
            transform: translateY(-2px);
        }

        /* Copy Button Style */
        .copy-button {
            background-color: #FFA500; /* Orange */
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            font-size: 0.9rem;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }
        .copy-button:hover {
            background-color: #EEDC82; /* Muted yellow */
            transform: translateY(-1px);
        }
        .copy-button.copied {
            background-color: #4CAF50; /* Green when copied */
            cursor: default;
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
            #main-content h1 {
                font-size: 2.5rem; /* Smaller hero title on mobile */
            }
            #main-content p {
                font-size: 1.25rem; /* Smaller hero subtitle on mobile */
            }
            .poet-entry, .genre-entry {
                padding: 1rem;
            }
            .poet-entry h3, .genre-entry h3 {
                font-size: 1.25rem;
            }
            .poetry-card .p-6 {
                padding: 1rem; /* Smaller card padding on mobile */
            }
            .poetry-card h4 {
                font-size: 1.25rem; /* Smaller card title on mobile */
            }
            .text-5xl { /* Section titles */
                font-size: 2rem;
            }
            .text-4xl { /* Newsletter title */
                font-size: 1.75rem;
            }
            .text-xl { /* Newsletter subtitle */
                font-size: 0.9rem;
            }
            .footer-links {
                flex-direction: column;
                gap: 0.5rem;
            }
            .poem-text {
                font-size: 0.9rem; /* Slightly smaller poem text on mobile */
            }
            .back-button {
                padding: 0.6rem 1.2rem;
                font-size: 0.9rem;
            }
            .copy-button {
                padding: 0.4rem 0.8rem;
                font-size: 0.8rem;
            }
        }

        /* Adjustments for tablets (iPad) */
        @media (min-width: 769px) and (max-width: 1024px) {
            .header-frame {
                padding: 1.5rem 3rem;
            }
            #main-content h1 {
                font-size: 3.5rem;
            }
            #main-content p {
                font-size: 1.75rem;
            }
            .poetry-card h4 {
                font-size: 1.5rem;
            }
            .text-5xl {
                font-size: 3rem;
            }
            .text-4xl {
                font-size: 2rem;
            }
            .text-xl {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <header id="main-header" class="fixed top-4 left-1/2 -translate-x-1/2 w-full z-50 transition-all duration-300 ease-in-out header-visible">
        <div class="header-frame">
            <nav class="flex flex-col items-center">
                <div class="flex flex-col md:flex-row justify-between items-center w-full mb-4 md:mb-0">
                    <div>
                        <a href="#" id="home-link" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            موسوعة الشعر الشعبي العراقي
                        </a>
                    </div>
                    <ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">
                        <li><a href="#" id="nav-poets" class="nav-link text-lg font-medium">الشعراء</a></li>
                        <li><a href="#" id="nav-genres" class="nav-link text-lg font-medium">أنواع الشعر</a></li>
                        <li><a href="#footer-copyright" class="nav-link text-lg font-medium">حقوق الطبع والنشر</a></li>
                    </ul>
                </div>
                <div class="relative w-full mt-4">
                    <input type="text" id="searchInput" placeholder="ابحث عن شاعر أو قصيدة..." class="search-input w-full p-3 md:p-4 text-lg border border-gray-300 rounded-full focus:ring-0 text-right pr-12">
                    <button class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500 hover:text-orange-500 transition duration-300 text-xl" aria-label="بحث">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </nav>
        </div>
    </header>

    <main id="main-content" class="container mx-auto py-16 px-6 md:px-12 mt-32">
        <section id="home-section" class="flex flex-col items-center justify-center text-center">
            <h1 class="text-5xl md:text-6xl font-extrabold text-gray-800 mb-6 leading-tight animate-fade-in">
                مرحبًا بك في <span class="text-orange-500">موسوعة الشعر الشعبي العراقي</span>
            </h1>
            <p class="text-xl md:text-2xl text-gray-600 mb-10 animate-fade-in animation-delay-200">
                بوابة لأروع القصائد وأشهر الشعراء الذين خطوا تاريخ العراق بكلماتهم.
            </p>

            <section id="poets-directory" class="w-full">
                <h2 class="text-4xl font-bold text-gray-800 text-center mb-10">الشعراء العراقيون</h2>
                <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-6">
                    <a href="#" data-poet-id="muzaffar-alnawab" class="poet-entry">
                        <h3 class="text-gray-800">مظفر النواب</h3>
                    </a>
                    <a href="#" data-poet-id="arian-alsayed" class="poet-entry">
                        <h3 class="text-gray-800">عريان السيد خلف</h3>
                    </a>
                    <a href="#" data-poet-id="kadhim-alkatea" class="poet-entry">
                        <h3 class="text-gray-800">كاظم اسماعيل الكاطع</h3>
                    </a>
                    <a href="#" data-poet-id="samir-sbeih" class="poet-entry">
                        <h3 class="text-gray-800">سمير صبيح</h3>
                    </a>
                    <a href="#" data-poet-id="jabbar-rasheed" class="poet-entry">
                        <h3 class="text-gray-800">جبار رشيد</h3>
                    </a>
                    <a href="#" data-poet-id="ali-rasham" class="poet-entry">
                        <h3 class="text-gray-800">علي رشم</h3>
                    </a>
                    <a href="#" data-poet-id="nazem-alhashi" class="poet-entry">
                        <h3 class="text-gray-800">ناظم الحاشي</h3>
                    </a>
                    <a href="#" data-poet-id="raheem-almaliki" class="poet-entry">
                        <h3 class="text-gray-800">رحيم المالكي</h3>
                    </a>
                    <a href="#" data-poet-id="abd-alhussein-alhalfy" class="poet-entry">
                        <h3 class="text-gray-800">عبد الحسين الحلفي</h3>
                    </a>
                    <a href="#" data-poet-id="ahmed-matar" class="poet-entry">
                        <h3 class="text-gray-800">أحمد مطر</h3>
                    </a>
                    <a href="#" data-poet-id="saheb-aldawiri" class="poet-entry">
                        <h3 class="text-gray-800">صاحب الضويري</h3>
                    </a>
                     <a href="#" data-poet-id="ehab-almaliki" class="poet-entry">
                        <h3 class="text-gray-800">إيهاب المالكي</h3>
                    </a>
                    <a href="#" data-poet-id="mohammad-alghabban" class="poet-entry">
                        <h3 class="text-gray-800">محمد الغبّان</h3>
                    </a>
                </div>
            </section>

            <section id="poetry-genres" class="w-full mt-16">
                <h2 class="text-4xl font-bold text-gray-800 text-center mb-10">أقسام الشعر الشعبي</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <a href="#" data-genre-id="love-romantic" class="genre-entry">
                        <h3 class="text-gray-800">شعر الحب والغزل والرومانسية</h3>
                    </a>
                    <a href="#" data-genre-id="bold-patriotic" class="genre-entry">
                        <h3 class="text-gray-800">شعر جريء ووطني</h3>
                    </a>
                    <a href="#" data-genre-id="social-wisdom" class="genre-entry">
                        <h3 class="text-gray-800">شعر اجتماعي وحكمة</h3>
                    </a>
                    <a href="#" data-genre-id="sad-melancholy" class="genre-entry">
                        <h3 class="text-gray-800">شعر حزين وشجن</h3>
                    </a>
                    <a href="#" data-genre-id="humorous-critical" class="genre-entry">
                        <h3 class="text-gray-800">شعر فكاهي ونقدي</h3>
                    </a>
                </div>
            </section>
        </section>

        <section id="dynamic-content" class="hidden-section flex flex-col items-start pt-8">
            <button id="back-button" class="back-button mb-8">
                <i class="fas fa-arrow-right ml-2"></i> العودة للرئيسية
            </button>
            <h2 id="dynamic-title" class="text-5xl font-bold text-gray-800 text-center w-full mb-12"></h2>
            <div id="poems-container" class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
                </div>
        </section>

        <section id="search-results-section" class="hidden-section flex flex-col items-start pt-8">
            <button id="back-from-search-button" class="back-button mb-8">
                <i class="fas fa-arrow-right ml-2"></i> العودة للرئيسية
            </button>
            <h2 class="text-5xl font-bold text-gray-800 text-center w-full mb-12">نتائج البحث</h2>
            <div id="search-results-container" class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
                </div>
            <p id="no-search-results" class="text-center text-gray-600 text-xl w-full mt-8 hidden">لا توجد نتائج مطابقة لبحثك.</p>
        </section>

    </main>

    <footer id="footer-copyright" class="bg-gray-900 py-10 px-6 md:px-12 text-center text-gray-400 mt-16">
        <div class="max-w-4xl mx-auto">
            <h2 class="text-3xl font-bold text-gray-200 mb-4">موسوعة الشعر الشعبي العراقي</h2>
            <p class="text-md text-gray-300 leading-relaxed mb-6">
                بوابتك الشاملة لأجمل القصائد والأبيات الشعرية لأبرز شعراء العراق العظام.<br>
                نسعى للحفاظ على هذا التراث الثقافي الغني وتقديمه لعشاق الشعر الأصيل.
                <br>
                © 2025 كرار حيدر. جميع الحقوق محفوظة.
            </p>

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

        // Data Structure for Poets and Poems
        const poetsData = {
            "muzaffar-alnawab": {
                name: "مظفر النواب",
                poems: [
                    { title: "للريل وحمد", text: "يا ريل صيح بقوة يا ريل،\nخلهم يسمعون الوجع بالريل.\nهاي الناس، هاي الوجوه التعبانة،\nمنين اجوها هيچي ضيم وويل؟\nيا ريل، گص الروس العدلة،\nخل نخلص من هالذل والهوان،\nلا تعاتبني بعد، دمي يفور،\nأنا الثاير وما أقبل بالظلم.", genres: ["bold-patriotic"] },
                    { title: "وحق روحي", text: "وحق روحي التذوبن بيك،\nما بطلن من الدمع عيوني.\nگلبي الك وحدك ينبض،\nوكل دگة بي تنادي باسمك.\nيا حلمي الجاي، يا كل عمري،\nبدونك دنيتي مو حلوة.\nخليني أعيش وياك،\nكل لحظة وكل سنين.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "ريحة خبز بالليل", text: "ريحة خبز بالليل، تعاتبني،\nتگلي مر بيه. يا ريل العشگ،\nوين أخذتني يا ريل؟\nالناس نامت، وأنا عيني مفتوحة.\nيا هموم الدنيا، شكد كافية؟\nگوم أرحم گلبي، يا ليل.\nوين الفرح؟ وين السعادة؟\nبس حزن بگلبي، ما يروح.", genres: ["sad-melancholy", "social-wisdom"] }
                ]
            },
            "arian-alsayed": {
                name: "عريان السيد خلف",
                poems: [
                    { title: "كلشي منك حلو", text: "كلشي منك حلو، حتى عذابك يا حبيبي،\nتظل بگلبي شعلة نار ما تطفي.\nيا أول عشگ، يا آخر محبة،\nروحي وروحي ليك تروح.\nشگد حاولت أنساك، ما گدرت،\nصورك بالبال، ما تفارگ عيني.\nأنا العايش على ذكرى حبك،\nوبدونك، دنيتي ما تسوى شي.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "يا ديرتي", text: "يا ديرتي الشالت هموم الناس،\nوجروحها ما طابت بيوم.\nكل بيت بيها قصة حزن،\nوكل روح بيها تشكي الظلوم.\nمتى الفرح يجي لدروبها؟\nوتنسى المر وتعيش بيوم.\nهاي الناس الطيبة الفقيرة،\nبس رب العباد يدري بظروفها.", genres: ["social-wisdom", "sad-melancholy"] }
                ]
            },
            "kadhim-alkatea": {
                name: "كاظم اسماعيل الكاطع",
                poems: [
                    { title: "يا روحي العذبتها", text: "يا روحي العذبتها، بيمن تاليها تروح،\nمحد غيري يفهمك، يا كل الجروح.\nأنا اللي سهرت الليالي وياك،\nوعيني ما نامت بس تشوفك.\nكل كلمة منك، أحفظها بگلبي،\nوكل نظرة عينك، هي دوا روحي.\nلا تعوفني وحدي، يا أغلى ناسي،\nترى بدونك، دنياي تصير ظلام.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "مر بيه", text: "مر بيه يا هوى العشاگ من تمر،\nوخليلي شي من ريحة هدومك.\nأنا بلياك وردة وماتت من العطش،\nوبدونك عيني ما تشوف النوم.\nكل العمر يمشي وأنتظر ملكاك،\nيا حلم السنين وكل دگة بگلبي.\nكون العمر يخلص وأنا بحضنك،\nلا أريد شي من الدنيا بس قربك.", genres: ["love-romantic"] }
                ]
            },
            "samir-sbeih": {
                name: "سمير صبيح",
                poems: [
                    { title: "ليش تمشي؟", text: "ليش تمشي؟ وادري عيونك تريدني،\nشگد ما مشيت بيا وطن... روحي تظل يمك.\nالدمعة بعيني ما تنشف،\nوبعدك أبد ما نمت ليلة.\nكل طيف يمر بيه، أحسبه إنت،\nوأركض وراه وألگاني وهم.\nيا ريت الزمن يرجع،\nوترجعلي ضحكة سنيني.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "يا دنيا شبية", text: "يا دنيا شبية ما تخلصين،\nويا روحي شبيچ ما تفرحين.\nكل يوم يكبر جرحي بلياچ،\nوصار الضحك ما يلوگ لعيوني.\nأنا المكتوبلي أظل بهمومي،\nوالحسرة بگلبي ما تفارگني.\nيا ريت الموت يجي ويخلصني،\nمن دنيا ما بيها أي شي يسعدني.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "ما ريدك", text: "ما ريدك بعد لو صرت ملك الموت،\nولتردلي ولا تسأل على حالي.\nكسرت گلبي وخذيت الروح مني،\nتاليها بعتني بأرخص ليالي.\nخليني وحيد، وحدي أحسنلي،\nالجرح يطيب لو صار وگته.\nعيني تشوفك بس گلبي ينساك،\nما اريدك تجي، كافي العذاب.", genres: ["sad-melancholy"] }
                ]
            },
            "jabbar-rasheed": {
                name: "جبار رشيد",
                poems: [
                    { title: "يا أول عشگ", text: "يا أول عشگ حنّيتله وعيني بكتله دموع،\nيا آخر نفس بضلوعي ظل بيّه يروح ويعود.\nشلون أنسى الليالي البيها چنت وياك؟\nشلون أطرد خيالك من يجي بجروحي؟\nروحي بيك تتوسّل، تعال ارجعلي.\nعمري بدونك ما يسوى ولا يوم.\nيا بعد كل ناسي وهلي، يا أغلى من الروح،\nلو تدري شگد أحبك، ما تبتعد عني.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "يا ليل الشوگ", text: "يا ليل الشوگ، بيا درب وديتني،\nودمعي يسيل على الخدين.\nتعبت روحي من كثر الونين،\nومحد يگدر يفهمني يا ناس.\nأنا الماشي دروب الحب وحدي،\nوقلبي ينزف من كثر الجراح.\nيا دنيتي كافي هجر وبعد،\nردولي حبيبي، كافي دموع.", genres: ["sad-melancholy"] }
                ]
            },
            "ali-rasham": {
                name: "علي رشم",
                poems: [
                    { title: "دمي يحكي", text: "دمي يحكي قصة وطن،\nبيها التضحية صارت فن.\nما خفت من الموت لحظة،\nروحي فدوة لتراب الوطن.\nلو كل قطرة دم تصير شراع،\nأوصلك يا عراق لأعلى مكان.\nأنا ابنك يا دجلة والفرات،\nترابك أغلى من الذهب، يا أغلى الأوطان.", genres: ["bold-patriotic"] }
                ]
            },
            "nazem-alhashi": {
                name: "ناظم الحاشي",
                poems: [
                    { title: "يا روحي", text: "يا روحي لا تحبين وتعبين،\nتراهم مو أهل وعد ولا يوفون.\nشگد ضحيت لأجلهم، ما دروا،\nتاليها تركوني وحيد بحزني.\nيا گلبي لا تلومني، ما بيدي،\nهي هاي الدنيا، يوم وياك ويوم عليك.\nعيش لنفسك، اترك الماضي،\nباچر يجي والكل ينسونك.", genres: ["social-wisdom", "sad-melancholy"] }
                ]
            },
            "raheem-almaliki": {
                name: "رحيم المالكي",
                poems: [
                    { title: "مشت روحي", text: "مشت روحي وعفتها بيدك،\nعساني ما مشيت خطوة بلياك.\nكل درب أمشي، أحس خطواتي وياك،\nوكل دگة بگلبي تنادي باسمك.\nيا عيني لا تبچين بعد،\nترا الدمع يخلص ويظل الجرح.\nأنا الما گدرت أعيش بلياك،\nروحي تطلع مني لو شفتك.", genres: ["love-romantic", "sad-melancholy"] }
                ]
            },
            "abd-alhussein-alhalfy": {
                name: "عبد الحسين الحلفي",
                poems: [
                    { title: "يا گلبي", text: "يا گلبي شبيك ما ترتاح؟\nمن كثر الهموم والحزن.\nأنا اللي گضيت عمري حسرات،\nوالفرح ما مر بيه ولا يوم.\nيا دنيتي كافي عذاب،\nروحي ملت من كثر الآهات.\nبس الصبر بگلبي ظل،\nأنتظر الفرج، يا رب.", genres: ["sad-melancholy", "social-wisdom"] }
                ]
            },
            "ahmed-matar": {
                name: "أحمد مطر",
                poems: [
                    { title: "نحن باقون", text: "نحن باقون... والأسماء قد تتغير،\nلكن وجه العدو لا يتغير.\nنحن صوت الأرض، صوت الشعب،\nمن تحت الركام، من لهيب النار.\nلا تظنوا أننا قد متنا،\nفنحن الشجر الذي لا يموت.\nكلما قطعوا منا غصناً،\nنبتت آلاف الأغصان من جديد.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "لا تشتروا العز", text: "لا تشتروا العز ببيع الأرض،\nفالبيع بيع الروح، بيع الشرف.\nالوطن ليس سوقاً للمساومة،\nولا سلعة تباع وتشترى.\nحافظوا عليه، فهو دمكم،\nفهو شرفكم، وهو عزكم.\nفلا قيمة لأرض تبيعونها،\nإذا ما ضاع فيها العز والحرف.", genres: ["bold-patriotic", "social-wisdom"] }
                ]
            },
            "saheb-aldawiri": {
                name: "صاحب الضويري",
                poems: [
                    { title: "بگت روحي", text: "بگت روحي ودمعي يجرن عليك،\nيا ليل الشوگ، شسويت بيّه.\nأنا بلياك وردة ذبلت،\nوالگلب من فرگاك مليته.\nترد الروح لو ردّيت،\nوكل فرحة تجي لو شفتك.\nيا أغلى من روحي، يا كل عمري،\nشگد مشتاگ لشوفتك يا حبيبي.", genres: ["love-romantic", "sad-melancholy"] }
                ]
            },
            "ehab-almaliki": {
                name: "إيهاب المالكي",
                poems: [
                    { title: "خلص كلشي", text: "خلص كلشي بلياك، والوكت راح،\nوبقت روحي الك، ما تريد سواك.\nأنا اللي تعبت من كثر البچي،\nوالعين ما شافت غيرك إنت.\nيا گلبي لا تلومني على حبي،\nهذا هو العشگ، مو بيدي ولا بيدك.\nبس الحسرة بگلبي، ما تروح،\nوالدمعة بعيني، ما تنشف ابد.", genres: ["sad-melancholy", "love-romantic"] }
                ]
            },
            "mohammad-alghabban": {
                name: "محمد الغبّان",
                poems: [
                    { title: "عصفور باليد", text: "عصفور باليد، أحسن من عشره على الشجر،\nوهذا مثل يگولونه، يا ناس، بگلبي.<br>\nلا تركض ورا السراب، تتعب،\nوخليك قنوع باللي موجود عندك.\nالدنيا ما بيها أمان، تتغير كل يوم،\nواللي يبيعك، باعه، لا تشتريه.\nاحفظ نفسك من الشرور،\nوعيش بسلام، ويا رب. ", genres: ["social-wisdom"] }
                ]
            }
        };

        const genresData = {
            "love-romantic": {
                name: "شعر الحب والغزل والرومانسية",
                poemIds: [
                    { poetId: "muzaffar-alnawab", poemTitle: "وحق روحي" },
                    { poetId: "arian-alsayed", poemTitle: "كلشي منك حلو" },
                    { poetId: "kadhim-alkatea", poemTitle: "يا روحي العذبتها" },
                    { poetId: "kadhim-alkatea", poemTitle: "مر بيه" },
                    { poetId: "samir-sbeih", poemTitle: "ليش تمشي؟" },
                    { poetId: "jabbar-rasheed", poemTitle: "يا أول عشگ" },
                    { poetId: "raheem-almaliki", poemTitle: "مشت روحي" },
                    { poetId: "saheb-aldawiri", poemTitle: "بگت روحي" },
                    { poetId: "ehab-almaliki", poemTitle: "خلص كلشي" }
                ]
            },
            "bold-patriotic": {
                name: "شعر جريء ووطني",
                poemIds: [
                    { poetId: "muzaffar-alnawab", poemTitle: "للريل وحمد" },
                    { poetId: "ali-rasham", poemTitle: "دمي يحكي" },
                    { poetId: "ahmed-matar", poemTitle: "نحن باقون" },
                    { poetId: "ahmed-matar", poemTitle: "لا تشتروا العز" }
                ]
            },
            "social-wisdom": {
                name: "شعر اجتماعي وحكمة",
                poemIds: [
                    { poetId: "muzaffar-alnawab", poemTitle: "ريحة خبز بالليل" },
                    { poetId: "arian-alsayed", poemTitle: "يا ديرتي" },
                    { poetId: "samir-sbeih", poemTitle: "يا دنيا شبية" },
                    { poetId: "nazem-alhashi", poemTitle: "يا روحي" },
                    { poetId: "abd-alhussein-alhalfy", poemTitle: "يا گلبي" },
                    { poetId: "ahmed-matar", poemTitle: "نحن باقون" },
                    { poetId: "ahmed-matar", poemTitle: "لا تشتروا العز" },
                    { poetId: "mohammad-alghabban", poemTitle: "عصفور باليد" }
                ]
            },
            "sad-melancholy": {
                name: "شعر حزين وشجن",
                poemIds: [
                    { poetId: "muzaffar-alnawab", poemTitle: "وحق روحي" },
                    { poetId: "muzaffar-alnawab", poemTitle: "ريحة خبز بالليل" },
                    { poetId: "arian-alsayed", poemTitle: "كلشي منك حلو" },
                    { poetId: "arian-alsayed", poemTitle: "يا ديرتي" },
                    { poetId: "kadhim-alkatea", poemTitle: "يا روحي العذبتها" },
                    { poetId: "samir-sbeih", poemTitle: "ليش تمشي؟" },
                    { poetId: "samir-sbeih", poemTitle: "يا دنيا شبية" },
                    { poetId: "samir-sbeih", poemTitle: "ما ريدك" },
                    { poetId: "jabbar-rasheed", poemTitle: "يا أول عشگ" },
                    { poetId: "jabbar-rasheed", poemTitle: "يا ليل الشوگ" },
                    { poetId: "nazem-alhashi", poemTitle: "يا روحي" },
                    { poetId: "raheem-almaliki", poemTitle: "مشت روحي" },
                    { poetId: "abd-alhussein-alhalfy", poemTitle: "يا گلبي" },
                    { poetId: "saheb-aldawiri", poemTitle: "بگت روحي" },
                    { poetId: "ehab-almaliki", poemTitle: "خلص كلشي" }
                ]
            },
            "humorous-critical": {
                name: "شعر فكاهي ونقدي",
                poemIds: [
                    // Add humorous/critical poems here later if available
                ]
            }
        };


        const homeSection = document.getElementById('home-section');
        const dynamicContentSection = document.getElementById('dynamic-content');
        const searchResultsSection = document.getElementById('search-results-section');
        const dynamicTitle = document.getElementById('dynamic-title');
        const poemsContainer = document.getElementById('poems-container');
        const backButton = document.getElementById('back-button');
        const backFromSearchButton = document.getElementById('back-from-search-button');
        const searchInput = document.getElementById('searchInput');
        const searchResultsContainer = document.getElementById('search-results-container');
        const noSearchResults = document.getElementById('no-search-results');
        
        // Function to hide all main sections
        function hideAllSections() {
            homeSection.classList.add('hidden-section');
            dynamicContentSection.classList.add('hidden-section');
            searchResultsSection.classList.add('hidden-section');
        }

        // Function to show home section
        function showHomeSection() {
            hideAllSections();
            homeSection.classList.remove('hidden-section');
            window.scrollTo({ top: 0, behavior: 'smooth' }); // Scroll to top
            searchInput.value = ''; // Clear search input
        }

        // Function to display poems for a poet
        function displayPoetPoems(poetId) {
            hideAllSections();
            dynamicContentSection.classList.remove('hidden-section');
            const poet = poetsData[poetId];
            dynamicTitle.textContent = `قصائد الشاعر ${poet.name}`;
            poemsContainer.innerHTML = ''; // Clear previous poems

            if (poet && poet.poems.length > 0) {
                poet.poems.forEach(poem => {
                    const poemCard = `
                        <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                            <div class="p-6">
                                <h4 class="text-2xl font-semibold text-gray-800 mb-2">${poem.title}</h4>
                                <p class="text-lg text-gray-700 mb-4">للشاعر: ${poet.name}</p>
                                <div class="poem-text text-gray-800">${poem.text}</div>
                                <button class="copy-button mt-4" data-poem-text="${poem.text}" aria-label="نسخ القصيدة">
                                    <i class="fas fa-copy ml-2"></i> نسخ القصيدة
                                </button>
                            </div>
                        </div>
                    `;
                    poemsContainer.insertAdjacentHTML('beforeend', poemCard);
                });
            } else {
                poemsContainer.innerHTML = `<p class="text-center text-gray-600 text-xl col-span-full">لا توجد قصائد لهذا الشاعر حالياً.</p>`;
            }
            window.scrollTo({ top: 0, behavior: 'smooth' }); // Scroll to top
            addCopyButtonListeners();
        }

        // Function to display poems for a genre
        function displayGenrePoems(genreId) {
            hideAllSections();
            dynamicContentSection.classList.remove('hidden-section');
            const genre = genresData[genreId];
            dynamicTitle.textContent = genre.name;
            poemsContainer.innerHTML = ''; // Clear previous poems

            if (genre && genre.poemIds.length > 0) {
                genre.poemIds.forEach(poemRef => {
                    const poet = poetsData[poemRef.poetId];
                    if (poet) {
                        const poem = poet.poems.find(p => p.title === poemRef.poemTitle);
                        if (poem) {
                            const poemCard = `
                                <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                                    <div class="p-6">
                                        <h4 class="text-2xl font-semibold text-gray-800 mb-2">${poem.title}</h4>
                                        <p class="text-lg text-gray-700 mb-4">للشاعر: ${poet.name}</p>
                                        <div class="poem-text text-gray-800">${poem.text}</div>
                                        <button class="copy-button mt-4" data-poem-text="${poem.text}" aria-label="نسخ القصيدة">
                                            <i class="fas fa-copy ml-2"></i> نسخ القصيدة
                                        </button>
                                    </div>
                                </div>
                            `;
                            poemsContainer.insertAdjacentHTML('beforeend', poemCard);
                        }
                    }
                });
            } else {
                poemsContainer.innerHTML = `<p class="text-center text-gray-600 text-xl col-span-full">لا توجد قصائد في هذا القسم حالياً.</p>`;
            }
            window.scrollTo({ top: 0, behavior: 'smooth' }); // Scroll to top
            addCopyButtonListeners();
        }

        // Add event listeners for Poet entries
        document.querySelectorAll('.poet-entry').forEach(entry => {
            entry.addEventListener('click', function(event) {
                event.preventDefault();
                const poetId = this.dataset.poetId;
                displayPoetPoems(poetId);
            });
        });

        // Add event listeners for Genre entries
        document.querySelectorAll('.genre-entry').forEach(entry => {
            entry.addEventListener('click', function(event) {
                event.preventDefault();
                const genreId = this.dataset.genreId;
                displayGenrePoems(genreId);
            });
        });

        // Back button functionality
        backButton.addEventListener('click', showHomeSection);
        backFromSearchButton.addEventListener('click', showHomeSection);

        // Header Navigation Links
        document.getElementById('home-link').addEventListener('click', function(event) {
            event.preventDefault();
            showHomeSection();
        });
        document.getElementById('nav-poets').addEventListener('click', function(event) {
            event.preventDefault();
            showHomeSection();
            document.getElementById('poets-directory').scrollIntoView({ behavior: 'smooth' });
        });
        document.getElementById('nav-genres').addEventListener('click', function(event) {
            event.preventDefault();
            showHomeSection();
            document.getElementById('poetry-genres').scrollIntoView({ behavior: 'smooth' });
        });

        // Copy button functionality
        function addCopyButtonListeners() {
            document.querySelectorAll('.copy-button').forEach(button => {
                button.addEventListener('click', function() {
                    const poemText = this.dataset.poemText;
                    navigator.clipboard.writeText(poemText).then(() => {
                        const originalText = this.innerHTML;
                        this.innerHTML = '<i class="fas fa-check ml-2"></i> تم النسخ!';
                        this.classList.add('copied');
                        setTimeout(() => {
                            this.innerHTML = originalText;
                            this.classList.remove('copied');
                        }, 2000);
                    }).catch(err => {
                        console.error('Failed to copy text: ', err);
                    });
                });
            });
        }

        // Search functionality
        searchInput.addEventListener('keyup', function() {
            const searchTerm = searchInput.value.toLowerCase().trim();
            searchResultsContainer.innerHTML = ''; // Clear previous results
            noSearchResults.classList.add('hidden'); // Hide no results message

            if (searchTerm === '') {
                showHomeSection(); // Go back to home if search is empty
                return;
            }

            hideAllSections();
            searchResultsSection.classList.remove('hidden-section');
            let hasResults = false;

            // Search through all poems
            for (const poetId in poetsData) {
                const poet = poetsData[poetId];
                poet.poems.forEach(poem => {
                    const poemContent = `${poem.title} ${poem.text} ${poet.name}`.toLowerCase();
                    if (poemContent.includes(searchTerm)) {
                        const poemCard = `
                            <div class="bg-white rounded-lg shadow-md overflow-hidden poetry-card fade-in-slide-rtl">
                                <div class="p-6">
                                    <h4 class="text-2xl font-semibold text-gray-800 mb-2">${poem.title}</h4>
                                    <p class="text-lg text-gray-700 mb-4">للشاعر: ${poet.name}</p>
                                    <div class="poem-text text-gray-800">${poem.text}</div>
                                    <button class="copy-button mt-4" data-poem-text="${poem.text}" aria-label="نسخ القصيدة">
                                        <i class="fas fa-copy ml-2"></i> نسخ القصيدة
                                    </button>
                                </div>
                            </div>
                        `;
                        searchResultsContainer.insertAdjacentHTML('beforeend', poemCard);
                        hasResults = true;
                    }
                });
            }

            if (!hasResults) {
                noSearchResults.classList.remove('hidden');
            }
            window.scrollTo({ top: 0, behavior: 'smooth' }); // Scroll to top
            addCopyButtonListeners(); // Add copy listeners to new search results
        });

        // Initialize the view
        showHomeSection();
    </script>
</body>
</html>

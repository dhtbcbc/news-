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
    <!-- Font Awesome for icons -->
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
            .text-4xl { /* Section titles inside dynamic content */
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
            .text-4xl { /* Section titles inside dynamic content */
                font-size: 2rem;
            }
            .text-xl {
                font-size: 1rem;
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
                        <a href="#" id="home-link" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            موسوعة الشعر الشعبي العراقي
                        </a>
                    </div>
                    <!-- Navigation Bar -->
                    <ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">
                        <li><a href="#" id="nav-poets" class="nav-link text-lg font-medium">الشعراء</a></li>
                        <li><a href="#" id="nav-genres" class="nav-link text-lg font-medium">أنواع الشعر</a></li>
                        <li><a href="#footer-copyright" class="nav-link text-lg font-medium">حقوق الطبع والنشر</a></li>
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

    <!-- Main Content Area - This will dynamically switch content -->
    <main id="main-content" class="container mx-auto py-16 px-6 md:px-12 mt-32">

        <!-- Home Section (Default View) -->
        <section id="home-view" class="">
            <div class="flex flex-col items-center justify-center text-center mb-16">
                <h1 class="text-5xl md:text-6xl font-extrabold text-gray-800 mb-6 leading-tight animate-fade-in">
                    مرحبًا بك في <span class="text-orange-500">موسوعة الشعر الشعبي العراقي</span>
                </h1>
                <p class="text-xl md:text-2xl text-gray-600 animate-fade-in animation-delay-200">
                    بوابة لأروع القصائد وأشهر الشعراء الذين خطوا تاريخ العراق بكلماتهم.
                </p>
            </div>

            <!-- Poets Directory Section (main view) -->
            <section id="poets-directory-home" class="w-full mb-16">
                <h2 class="text-4xl font-bold text-gray-800 text-center mb-10">الشعراء العراقيون</h2>
                <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6">
                    <!-- Poet Entries will be dynamically populated by JS for cleaner HTML structure in data -->
                </div>
            </section>

            <!-- Poetry Genres Section (main view) -->
            <section id="poetry-genres-home" class="w-full">
                <h2 class="text-4xl font-bold text-gray-800 text-center mb-10">أقسام الشعر الشعبي</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Genre Entries will be dynamically populated by JS for cleaner HTML structure in data -->
                </div>
            </section>
        </section>

        <!-- Dynamic Content Section (Hidden by default, shows poet/genre poems) -->
        <section id="dynamic-content-view" class="hidden-section flex flex-col items-start pt-8">
            <button id="back-button" class="back-button mb-8">
                <i class="fas fa-arrow-right ml-2"></i> العودة للرئيسية
            </button>
            <h2 id="dynamic-title" class="text-4xl md:text-5xl font-bold text-gray-800 text-center w-full mb-12"></h2>
            <div id="poems-container" class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
                <!-- Poems will be loaded here dynamically -->
            </div>
        </section>

        <!-- Search Results Section (Hidden by default, shows search results) -->
        <section id="search-results-view" class="hidden-section flex flex-col items-start pt-8">
            <button id="back-from-search-button" class="back-button mb-8">
                <i class="fas fa-arrow-right ml-2"></i> العودة للرئيسية
            </button>
            <h2 class="text-4xl md:text-5xl font-bold text-gray-800 text-center w-full mb-12">نتائج البحث</h2>
            <div id="search-results-container" class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
                <!-- Search results will be loaded here -->
            </div>
            <p id="no-search-results" class="text-center text-gray-600 text-xl w-full mt-8 hidden">لا توجد نتائج مطابقة لبحثك.</p>
        </section>

    </main>

    <!-- Footer Section -->
    <footer id="footer-copyright" class="bg-gray-900 py-10 px-6 md:px-12 text-center text-gray-400 mt-16">
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

        // Data Structure for Poets and Poems (Extensive content)
        const poetsData = {
            "muzaffar-alnawab": {
                name: "مظفر النواب",
                poems: [
                    { title: "للريل وحمد", text: "يا ريل صيح بقوة يا ريل،\nخلهم يسمعون الوجع بالريل.\nهاي الناس، هاي الوجوه التعبانة،\nمنين اجوها هيچي ضيم وويل؟\nيا ريل، گص الروس العدلة،\nخل نخلص من هالذل والهوان،\nلا تعاتبني بعد، دمي يفور،\nأنا الثاير وما أقبل بالظلم.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "وحق روحي", text: "وحق روحي التذوبن بيك،\nما بطلن من الدمع عيوني.\nگلبي الك وحدك ينبض،\nوكل دگة بي تنادي باسمك.\nيا حلمي الجاي، يا كل عمري،\nبدونك دنيتي مو حلوة.\nخليني أعيش وياك،\nكل لحظة وكل سنين.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "ريحة خبز بالليل", text: "ريحة خبز بالليل، تعاتبني،\nتگلي مر بيه. يا ريل العشگ،\nوين أخذتني يا ريل؟\nالناس نامت، وأنا عيني مفتوحة.\nيا هموم الدنيا، شكد كافية؟\nگوم أرحم گلبي، يا ليل.\nوين الفرح؟ وين السعادة؟\nبس حزن بگلبي، ما يروح.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "أيها المتعبون", text: "أيها المتعبون من قعر السجون،\nوالجواري يمشين على جثث السنين.\nيا سيفاً يضرب الرقاب بلا سبب،\nومن يرى الحق يركع للطغاة.\nهذا الزمان قد خاب مسعاه،\nوالصامتون عن الحق هم كالشياطين.\nمضى عمرنا ونحن نبكي،\nعلى وطن باعوه بأرخص الثمن.", genres: ["bold-patriotic", "social-wisdom", "sad-melancholy"] },
                    { title: "كلما اقتربت", text: "كلما اقتربت منك، كلما ابتعدت،\nكأنك السراب الذي لا يُدرك.\nأنا الشاعر الذي يكتب القصائد،\nوهم يبيعون الحروف في السوق.\nيا دنيا كفى بنا دمعاً،\nفالعيون جفت من كثرة البكاء.\nوالقلوب قد ماتت فينا،\nولم يعد للحب فينا أي رجاء.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا وجع القلب", text: "يا وجع القلب ما ضل صبر،\nوالروح ذابت من كثر القهر.\nعشت أيامي بين الآهات،\nوالفرح ما زار دربي ولا مر.\nيا دنيا كافي عذابي،\nالجسد تعب والروح انكسر.\nمتى يجي الموت وياخذني،\nحتى أرتاح من هذا العمر.", genres: ["sad-melancholy"] },
                    { title: "الشمس لا تغيب", text: "الشمس لا تغيب عن وطني،\nحتى لو غابت كل شمس في الدنيا.\nالعراق يا دمي ويا نبضي،\nأنت الحياة وأنت كل المنى.\nمهما خانوا وتآمروا،\nستبقى رايتك عالية بالسما.\nفلا تهتموا لأقوال الحساد،\nفالعراق لا يهزم، يبقى دائماً هو الأقوى.", genres: ["bold-patriotic"] },
                    { title: "لو كان لي قلبان", text: "لو كان لي قلبان لعشت بحب،\nقلب يحب وآخر يُجرب.\nلكن بقلب واحد كيف أعيش؟\nوقد غاب عني من أحب.\nالخيانه طبع في بعض البشر،\nوالغدر يجري في عروقهم كالسم.\nيا من خدعتني وغدرت بي،\nسأعيش بعدك، ولن أتهزم.", genres: ["love-romantic", "betrayal-separation"] },
                    { title: "أنا الحقيقة", text: "أنا الحقيقة التي لا تختبئ،\nوصوتي لا يصمت أمام الباطل.\nأنا الشاعر الذي يكسر القيود،\nويرفع الرأس في وجه السلاسل.\nفلا تخافوا من كلمة الحق،\nفالحق هو الذي يكسر كل حاجز.\nسيأتي يوم، ويرى الجميع،\nأن الحق هو المنتصر، والباطل هو الهالك.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "رسالة إلى وطني", text: "رسالة إلى وطني يا عراق،\nمن قلب ينزف من كثر الأشواق.\nمتى تعود أيامك الخوالي؟\nويزول عنك هذا العذاب والضياع.\nأنا ابنك البار، ما خنتك،\nروحي فدوة لترابك، يا أغلى بقاع.\nسأظل أقاتل حتى آخر نفس،\nلتظل رايتك عالية، وتظل في القمة تضاحك.", genres: ["bold-patriotic"] }
                ]
            },
            "arian-alsayed": {
                name: "عريان السيد خلف",
                poems: [
                    { title: "كلشي منك حلو", text: "كلشي منك حلو، حتى عذابك يا حبيبي،\nتظل بگلبي شعلة نار ما تطفي.\nيا أول عشگ، يا آخر محبة،\nروحي وروحي ليك تروح.\nشگد حاولت أنساك، ما گدرت،\nصورك بالبال، ما تفارگ عيني.\nأنا العايش على ذكرى حبك،\nوبدونك، دنيتي ما تسوى شي.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "يا ديرتي", text: "يا ديرتي الشالت هموم الناس،\nوجروحها ما طابت بيوم.\nكل بيت بيها قصة حزن،\nوكل روح بيها تشكي الظلوم.\nمتى الفرح يجي لدروبها؟\nوتنسى المر وتعيش بيوم.\nهاي الناس الطيبة الفقيرة،\nبس رب العباد يدري بظروفها.", genres: ["social-wisdom", "sad-melancholy"] },
                    { title: "مدري شبية", text: "مدري شبية، لا أضحك ولا أبجي،\nمثل الطفل اللي ضاع من أمه.\nروحي معلقة بين السما والأرض،\nلا هي قادرة تطير ولا هي تتكلم.\nيا دنيا كافي قسوة،\nگلبي تعب من كثر الألم.\nأريد أرتاح، أريد أنام،\nوأنسى كلشي، وأنسى همومي.", genres: ["sad-melancholy"] },
                    { title: "عصفور الجناين", text: "عصفور الجناين حاچيني،\nمنين جبت هذا اللحن الحزين؟\nكل صوت منك يذكرني،\nبأيام مرت، ما ترجع سنين.\nيا زمان شگد ظالم،\nتاخذ من عدنا أغلى الحبيبين.\nنبقى وحدنا، نشكي الأيام،\nوالروح من الونين تصيح وين.", genres: ["sad-melancholy"] },
                    { title: "يا شوك العمر", text: "يا شوك العمر، يا دمعة العين،\nبعدك گلبي ما ينبض بالحنين.\nكل خطوة أمشيها بلياك،\nأحسها درب نهايته وين.\nالخيانة طعنت گلبي،\nوالوفا صار عملة ما تبين.\nيا دنيا كافي عذابي،\nصرت عايش بلا روحين.", genres: ["love-romantic", "betrayal-separation", "sad-melancholy"] },
                    { title: "حچي الناس", text: "حچي الناس مثل الموج،\nياخذ ويجيب، ما عنده حدود.\nخلهم يحچون، أنا ما يهمني،\nما دام ربي هو الوجود.\nالحكمة مو بالكثرة،\nبالقليل اللي يبقى ويفيد.\nعيش لضميرك، لربك،\nوالباقي كله وهم ووعود.", genres: ["social-wisdom"] },
                    { title: "ليل وظلام", text: "ليل وظلام، وگلبي يعاني،\nيا نوم تعال، گلبي ما ينام.\nأفكاري تتقاتل بداخل صدري،\nعلى حب راح، صار بس أحلام.\nيا گلبي لا تحن عليهم،\nتراهم خانوك، ما بيهم ذمام.\nانسى الماضي، وعيش لحظتك،\nترا اللي راح، ما يرجع بالسلام.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "على جروحي", text: "على جروحي داويت ناس،\nونسيت روحي وگلبي اللي عانى.\nالوفا صعب تلاگيه،\nوالخيانة طبع بأهل الزمانا.\nيا ليتني ما حبيتهم،\nولا شفت منهم ذاك العدوانا.\nصبرت وگلت باچر يزين،\nبس الأيام ما رضت تنسانا.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الفرح غايب", text: "الفرح غايب، والعمر يمشي،\nوالحزن ساكن بگلبي وعيوني.\nمن كثر ما شفت من الدنيا،\nصرت أريد بس ربي يهديني.\nيا صبر الروح، إلك أشكي،\nهموم الدنيا تزيدني جنوني.\nيا ناس كافي ظلم وظلال،\nبس رحمة من الله، يكفيني.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "وطن الجروح", text: "وطن الجروح يا عراق،\nشگد بكت عيوني لأجلك.\nكل شبر منك يحكي قصة،\nوبكل دمعة، أكتبلك أحبك.\nيا تاريخ مجدنا،\nمهما خانوا، سنبقى بجنبك.\nرايتك عالية، ما تنزل،\nيا تراب الوطن، فدوة لترابك.", genres: ["bold-patriotic", "sad-melancholy"] }
                ]
            },
            "kadhim-alkatea": {
                name: "كاظم اسماعيل الكاطع",
                poems: [
                    { title: "يا روحي العذبتها", text: "يا روحي العذبتها، بيمن تاليها تروح،\nمحد غيري يفهمك، يا كل الجروح.\nأنا اللي سهرت الليالي وياك،\nوعيني ما نامت بس تشوفك.\nكل كلمة منك، أحفظها بگلبي،\nوكل نظرة عينك، هي دوا روحي.\nلا تعوفني وحدي، يا أغلى ناسي،\nترى بدونك، دنياي تصير ظلام.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "مر بيه", text: "مر بيه يا هوى العشاگ من تمر،\nوخليلي شي من ريحة هدومك.\nأنا بلياك وردة وماتت من العطش،\nوبدونك عيني ما تشوف النوم.\nكل العمر يمشي وأنتظر ملكاك،\nيا حلم السنين وكل دگة بگلبي.\nكون العمر يخلص وأنا بحضنك،\nلا أريد شي من الدنيا بس قربك.", genres: ["love-romantic"] },
                    { title: "يا گلبي لا تبجي", text: "يا گلبي لا تبجي على الفات،\nترا الدمع ما يرجع اللي راح.\nعشت وياك أيام وسنين،\nوما شفت منك بس الجراح.\nخانوا الوعد، ونسوا الحب،\nوخلوني وحدي بنار الأشواق.\nيا ريتني ما حبيتهم،\nولا شفت منهم ذاك الفراق.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الصبر مفتاح الفرج", text: "الصبر مفتاح الفرج، يا روحي صبري،\nترا الدنيا هاي ما تدوم لأحد.\nاليوم الك باچر عليك،\nوالحكم بيد الله، هو الصمد.\nلا تتهور، ولا تضيق،\nترا ربك موجود، وهو السند.\nالظلم ما يدوم، والباطل يزول،\nوالحق هو اللي يظل، وما يتهدد.", genres: ["social-wisdom"] },
                    { title: "أنا العاشق", text: "أنا العاشق الذي لا ينام،\nوالعيون تسهر، تتمنى حلم.\nأحبك حباً، ما يوصفه كلام،\nيا أغلى من روحي، يا روحي والدم.\nكل لحظة بدونك، عذاب،\nوكل دقيقة، تمر كأنها ألف عام.\nمتى تجي وتداوي جروحي،\nيا شمس عمري، يا أجمل غرام.", genres: ["love-romantic"] },
                    { title: "الحياة دروس", text: "الحياة دروس، والزمن معلم،\nوكل يوم نتعلم شي جديد.\nلا تندم على شي فات،\nوعيش يومك، وسوي اللي يفيد.\nالناس مقامات، مو كل شخص،\nيستاهل الوفا والحب الشديد.\nخليك ذيب بين الذئاب،\nحتى ما تندم، وتبقى سعيد.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "جروحي تنزف", text: "جروحي تنزف، وما بيها طبيب،\nوالقلب مجروح، ما يرضى يطيب.\nمن كثر ما شفت من الخيانة،\nصرت أخاف حتى من القريب.\nيا زمان الوفا، وينك؟\nصار الغدر عملة، ما الها نصيب.\nيا دنيا كافي قسوة،\nخلي قلبي يرتاح، لا تعذبيه.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "ليل العشاگ", text: "ليل العشاگ، ساهر بيك،\nوالشوق بگلبي ما ينام.\nأتذكر أيامنا، كل لحظة،\nوأحس بوجودك، حتى بالأوهام.\nيا نجمة الليل، يا قمري،\nيا أغلى حب، يا أجمل غرام.\nأتمنى ترجع، وتداوي جروحي،\nوترجعلي الفرح، وتنسيني الآلام.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "دموع العين", text: "دموع العين، تجري مثل النهر،\nعلى ولف راح، وما يدري بالقهر.\nيا ريتني ما عرفته،\nولا شفت منه ذاك الغدر.\nالوفا خاين، والحب كذاب،\nوالدنيا كلها، تزيدني تعسر.\nيا رب أرحم بحالي،\nخلصني من هذا، كافي قهر.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "عيش حياتك", text: "عيش حياتك، لا تندم على شي،\nترا العمر يمشي، ما يرجع أبد.\nالفرحة لحظة، والحزن أيام،\nوالوفا نادر، ما تلاگيه بأحد.\nخليك قوي، لا تنكسر،\nترا الدنيا ما تستاهل دمع.\nعيش لكرامتك، ولنفسك،\nوالباقي كله وهم، وما ينفع.", genres: ["social-wisdom"] }
                ]
            },
            "samir-sbeih": {
                name: "سمير صبيح",
                poems: [
                    { title: "ليش تمشي؟", text: "ليش تمشي؟ وادري عيونك تريدني،\nشگد ما مشيت بيا وطن... روحي تظل يمك.\nالدمعة بعيني ما تنشف،\nوبعدك أبد ما نمت ليلة.\nكل طيف يمر بيه، أحسبه إنت،\nوأركض وراه وألگاني وهم.\nيا ريت الزمن يرجع،\nوترجعلي ضحكة سنيني.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "يا دنيا شبية", text: "يا دنيا شبية ما تخلصين،\nويا روحي شبيچ ما تفرحين.\nكل يوم يكبر جرحي بلياچ،\nوصار الضحك ما يلوگ لعيوني.\nأنا المكتوبلي أظل بهمومي،\nوالحسرة بگلبي ما تفارگني.\nيا ريت الموت يجي ويخلصني،\nمن دنيا ما بيها أي شي يسعدني.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "ما ريدك", text: "ما ريدك بعد لو صرت ملك الموت،\nولتردلي ولا تسأل على حالي.\nكسرت گلبي وخذيت الروح مني،\nتاليها بعتني بأرخص ليالي.\nخليني وحيد، وحدي أحسنلي،\nالجرح يطيب لو صار وگته.\nعيني تشوفك بس گلبي ينساك،\nما اريدك تجي، كافي العذاب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا أول محب", text: "يا أول محب روحي حبتك،\nويا آخر نفس بگلبي ظل بيك.\nمن يوم الشفتك، تغيرت حياتي،\nوصرت ما أفكر بغيرك ولا بيك.\nعيوني تنام وتصحه عليك،\nوأحلامي كلها، تذكرني بيك.\nيا حبي الأول، يا نصفي الثاني،\nبدونك روحي، ما ترتاح، ولا تبكي.", genres: ["love-romantic"] },
                    { title: "خيبة أمل", text: "خيبة أمل، من ناس چنت أثق بيهم،\nخانوا الوعد، وكسروا گلبي.<br>
                        عشرة عمر، راحت بليلة،\nوكل شي حلو، صار بس تعب.<br>
                        يا دنيا شگد غدارة،\nتضحكين على الواحد، وبعدين تبتليه.<br>
                        لكن أبد ما أنكسر،\nربي وياي، وهو اللي يقويني.", genres: ["betrayal-separation", "sad-melancholy", "social-wisdom"] },
                    { title: "درس من الحياة", text: "درس من الحياة، تعلمته،\nالطيب ما ينفع مع كل البشر.\nبعض البشر، ما يقدرون،\nوالوفا عندهم، أغلى من الدرر.\nعش لنفسك، واترك الماضي،\nترا اللي خانك، ما يستاهل العذر.\nعيش بسلام، ورفع راسك،\nترا العمر قصير، لا تضيعه بالقهر.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "ليل طويل", text: "ليل طويل، ما بيه نجمة،\nوالروح بلياك، صارت هدمه.<br>
                        الدمعة تجري، ما توگف،\nوالگلبي يصرخ، من كثر الندمه.<br>
                        يا ريتني ما شفتك،\nولا حبيت، ولا عرفت معنى الحب.<br>
                        صار الحب بگلبي، جمرة،\nتحرگني، وما تخلي بيا كلمه.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "يا وطن", text: "يا وطن، يا جرح ما يطيب،\nيا دمعة العين، يا صرخة غريب.<br>
                        كل يوم أسمع، أخبار جديدة،\nوالقلب ينزف، من هذا العجيب.<br>
                        خانوا بيك، وتركوك وحدك،\nواللي يحبك، ما عنده نصيب.<br>
                        لكن ستبقى، شامخاً،\nوعد الله، ما عنده كذيب.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "عهد ما يخون", text: "عهد ما يخون، تبقى بگلبي،\nيا أغلى من روحي، يا كل دنيتي.\nالوفا طبعي، ما أغيره،\nحتى لو خانتني، كل الناس.<br>
                        أنت الأول، وأنت الأخير،\nوغيرك أبد، ما أحب ولا أهوى.<br>
                        يا شمس عمري، يا ضوى عيني،\nتبقى بگلبي، ما تروح، ولا تنسى.", genres: ["love-romantic"] },
                    { title: "نصيحة", text: "نصيحة مني، لا تثق بأحد،\nترا الناس تتغير، مع كل زمن.<br>
                        اليوم صاحبك، باچر عدوك،\nوالأيام تثبتلك، هذا المثل.<br>
                        عيش لنفسك، ولضميرك،\nولا تسوي شي، يزعجك أبد.<br>
                        واللي ما يقدرك، اتركه،\nترا الحياة قصيرة، وما بيها نفع.", genres: ["social-wisdom", "betrayal-separation"] }
                ]
            },
            "jabbar-rasheed": {
                name: "جبار رشيد",
                poems: [
                    { title: "يا أول عشگ", text: "يا أول عشگ حنّيتله وعيني بكتله دموع،\nيا آخر نفس بضلوعي ظل بيّه يروح ويعود.\nشلون أنسى الليالي البيها چنت وياك؟\nشلون أطرد خيالك من يجي بجروحي؟\nروحي بيك تتوسّل، تعال ارجعلي.\nعمري بدونك ما يسوى ولا يوم.\nيا بعد كل ناسي وهلي، يا أغلى من الروح،\nلو تدري شگد أحبك، ما تبتعد عني.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "يا ليل الشوگ", text: "يا ليل الشوگ، بيا درب وديتني،\nودمعي يسيل على الخدين.\nتعبت روحي من كثر الونين،\nومحد يگدر يفهمني يا ناس.\nأنا الماشي دروب الحب وحدي،\nوقلبي ينزف من كثر الجراح.\nيا دنيتي كافي هجر وبعد،\nردولي حبيبي، كافي دموع.", genres: ["sad-melancholy"] },
                    { title: "لو تدري شكد أهواك", text: "لو تدري شگد أهواك، ما تگضي ليلة بدمع،\nلو تدري بروحي شظاملك حب ما يوم ينتهي.\nعيوني تسهر وتناطر جيتك،\nوروحي تفرفح لو سمعت اسمك.\nيا شمس عمري، يا ضوى سنيني،\nبدونك دنيتي ظلام حالك.\nإرجعلي، گلبي مشتاگلك،\nما أگدر أعيش لحظة بلياك.", genres: ["love-romantic"] },
                    { title: "ما ظن ترجعون", text: "ما ظن ترجعون، وياكم العمر فات،\nوالروح ملت من كثر الآهات.\nخانوا الوعد، ونسوا الحب،\nوخلوني وحدي بليلة ممات.\nيا ليتني ما حبيتهم،\nولا شفت منهم ذاك المات.\nأنا العايش على الذكريات،\nوالقلب ينزف من كثر الجراح.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "جرح الوفا", text: "جرح الوفا، ما يطيب بسهولة،\nترا اللي يخونك، ما يظل وفي.\nالأيام تثبتلك، منو الصادق،\nومنو اللي يمشي، مثل ظله ويختفي.\nيا گلبي اصبر، على البلوة،\nترا كل جرح، وله رب يشفي.\nعيش لكرامتك، وارفع راسك،\nترا اللي باعك، ما يستاهل الشفقة.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا طير", text: "يا طير طاير، وديني للحبيب،\nگوليله گلبي، ما ينام بلياك.\nكل لحظة تمر، كأنها ألف عام،\nوالروح تشتاگ، تتمنى ملكاك.\nيا أغلى من روحي، يا كل عمري،\nأنا بلياك، ما أگدر أعيش.\nترجعلي الحياة، لو شفتك،\nيا أملي، يا كل دنياي.", genres: ["love-romantic"] },
                    { title: "ظلم البشر", text: "ظلم البشر، ما ينتهي بيوم،\nوالقلوب صارت، كلها سواد.\nالحق ما يظهر، والباطل يسود،\nوالأبرياء، ما بيهم منقاد.\nيا دنيا كافي، ظلم وعذاب،\nترا الأرواح، ملت من هذا العناد.\nوين العدالة؟ وين الحق؟\nصار الوطن، مثل بيت الأعناد.", genres: ["social-wisdom", "bold-patriotic"] },
                    { title: "عيني بكت", text: "عيني بكت، دمعها صار نهر،\nعلى أيام مرت، ما ترجع بعد.\nالوفا غاب، والصدق راح،\nوكلشي تغير، صار مثل الفهد.\nيا حظي العاثر، ما عندي غيره،\nوالدنيا ضاگت، ما بيها أحد.\nبس ربك موجود، يسمع،\nوهو اللي يعوض، واللي يسعد.", genres: ["sad-melancholy"] },
                    { title: "حبك قدر", text: "حبك قدر، ما أگدر أغيره،\nيا نبض گلبي، يا أجمل حلم.\nمن يوم اللي شفتك، عيني ما نامت،\nوغيرك أبد، ما عرفت طعم.\nيا شمس عمري، يا ضوى أيامي،\nأنا بلياك، مثل وردة بلا دم.\nتبقى بگلبي، طول العمر،\nيا حبيبي، يا أغلى اسم.", genres: ["love-romantic"] },
                    { title: "ضاعت الروح", text: "ضاعت الروح، وياك يا حبيبي،\nولم أجد لها بعدك أي مكان.\nالحياة بدونك، موت،\nوالعيون بكت، من كثر الأحزان.\nيا من بعتني، بأرخص الأثمان،\nلن أسامحك، مهما طال الزمان.\nالخيانة طبعك، والغدر سيفك،\nوالوفا، ما يعرف طريقك، يا خوان.", genres: ["betrayal-separation", "sad-melancholy"] }
                ]
            },
            "ali-rasham": {
                name: "علي رشم",
                poems: [
                    { title: "دمي يحكي", text: "دمي يحكي قصة وطن،\nبيها التضحية صارت فن.\nما خفت من الموت لحظة،\nروحي فدوة لتراب الوطن.\nلو كل قطرة دم تصير شراع،\nأوصلك يا عراق لأعلى مكان.\nأنا ابنك يا دجلة والفرات،\nترابك أغلى من الذهب، يا أغلى الأوطان.", genres: ["bold-patriotic"] },
                    { title: "أنا العراقي", text: "أنا العراقي، وعراقيتي تاج،\nما أنحني لغير الله، ولا أذل.\nروحي فدوة لترابك يا وطن،\nولأجلك روحي، ما بيها كل ملل.\nالتاريخ يشهد، على أصالتنا،\nوالشجاعة طبعنا، وما بيها جدل.\nسنبقى سادة، وفوق الجميع،\nوالعراق يبقى، هو الأصل.", genres: ["bold-patriotic"] },
                    { title: "تراب الوطن", text: "تراب الوطن، أقدس من الروح،\nوكل قطرة دم، تسقي هذا الجرح.\nعلي رشم، ما ينسى بلاده،\nوبدمي أكتب، أحبك يا صبح.\nيا شمس المجد، لا تغيبين،\nفالعراق يبقى، هو اللي يفرح.\nنمشي وراسنا، مرفوع،\nلأجل العراق، كل صعب نربح.", genres: ["bold-patriotic"] },
                    { title: "يا رفاق الدرب", text: "يا رفاق الدرب، لا تنسوني،\nأنا اللي ضحيت، لأجل الوطن.\nروحي طلعت، فدوة لعيونكم،\nودمي سال، على تراب الكفن.\nلا تخذلوا، دماء الشهداء،\nحافظوا على العراق، من كل محن.\nكونوا يداً واحدة،\nضد كل غازي، ضد كل فتن.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "صوت الشهيد", text: "صوت الشهيد، ما يموت أبداً،\nيبقى يصدح، في كل مكان.\nيناديكم، يا أبناء وطني،\nحافظوا على الأرض، من الخوان.\nلا تسلموا، ذرة تراب،\nفالعراق أمانة، من رب الأكوان.\nسنبقى صامدين، بوجه الأعداء،\nلأجل العراق، نضحي بكل الأثمان.", genres: ["bold-patriotic"] },
                    { title: "أمنية شهيد", text: "أمنية شهيد، أن يبقى وطني،\nحراً أبيّاً، شامخ الهامة.\nلا ينحني لظالم، ولا يخضع،\nويبقى العراق، هو العلامة.\nأوصيكم بالوحدة،\nففيها القوة، وفيها السلامة.\nكونوا يداً واحدة،\nلتحموا الوطن، وترفعوا أعلامه.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "أحلم بوطن", text: "أحلم بوطن، يعيش بسلام،\nبعيد عن الحروب، وعن الظلام.\nالشعب مرتاح، والخير يعم،\nوكل واحد عايش، بحب ووئام.\nهذا حلمي، وهذا أملي،\nيا رب حقق لي، هذا المرام.\nفالعراق يستاهل، كل خير،\nوأهله يستاهلون، أطيب الأيام.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "رسالتي الأخيرة", text: "رسالتي الأخيرة، يا أهلي،\nلا تنسوني، ولا تنسوا دمي.\nلقد مت، لأجل هذا الوطن،\nليعيش حراً، ويزول عنه الهم.<br>\nكونوا أوفياء، لترابكم،\nولا تهابوا الموت، ولا تخافوا السم.\nالنصر قادم، لا محالة،\nفالعراق سينهض، من تحت الركام.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "لأجل عيون العراق", text: "لأجل عيون العراق، روحي فدوة،\nولأجل ترابه، أضحي بكل قوة.<br>\nلا يهمني الموت، ولا الخوف،\nأنا ابن العراق، وما أتركه أبد.<br>\nيا شعب العراق، يا أهلي،\nالوفا طبعكم، يا أهل الشهامة.\nسنبني العراق، من جديد،\nونرفع رايته، في كل قمامة.", genres: ["bold-patriotic"] },
                    { title: "عهد الدم", text: "عهد الدم، بيني وبينك،\nيا تراب الوطن، يا أغلى ما عندي.<br>\nسأظل أقاتل، حتى آخر نفس،\nلأجل عينيك، يا تراب جدي.<br>\nلا يهمني الموت، ولا الظلم،\nفالحياة بدونك، لا تسوى عندي.<br>\nيا عراق، اسمك في دمي،\nولأجلك، أفدي روحي، وبكل جهدي.", genres: ["bold-patriotic"] }
                ]
            },
            "nazem-alhashi": {
                name: "ناظم الحاشي",
                poems: [
                    { title: "يا روحي", text: "يا روحي لا تحبين وتعبين،\nتراهم مو أهل وعد ولا يوفون.\nشگد ضحيت لأجلهم، ما دروا،\nتاليها تركوني وحيد بحزني.\nيا گلبي لا تلومني، ما بيدي،\nهي هاي الدنيا، يوم وياك ويوم عليك.\nعيش لنفسك، اترك الماضي،\nباچر يجي والكل ينسونك.", genres: ["social-wisdom", "sad-melancholy", "betrayal-separation"] },
                    { title: "خانتني الظنون", text: "خانتني الظنون، وراح اللي أحبه،\nوالقلب مجروح، ما يطيب.<br>
                        الوفا خانني، والغدر طعنني،\nوالصبر ما ضل، ولا لي نصيب.<br>
                        يا ليتني ما حبيتهم،\nولا شفت منهم، هذا العذيب.<br>
                        صرت عايش، بليلي ونهاري،\nمثل الغريب اللي، ما عنده حبيب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "درس الأيام", text: "درس الأيام، قاسي ومؤلم،\nيعلمك قيمة اللي يوفون.<br>
                        لا تثق بالناس كلها،\nفبعضهم، يغدرون ويخونون.<br>
                        حافظ على نفسك، من الشرور،\nوعيش بضميرك، مهما يكونون.<br>
                        ترا اللي يحبك، يظل وياك،\nواللي يبيعك، ما يستاهلون.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "دمعة حسرة", text: "دمعة حسرة، تجري على الخدين،\nعلى عمر فات، بلياك يا زين.<br>
                        الروح ذابت، من كثر الشوق،\nوالقلب ينبض، بس بالحنين.<br>
                        متى تجي وتداوي جروحي،\nيا شمس عمري، يا نور العين.<br>
                        أنا بلياك، ما أگدر أعيش،\nترا روحي، تصرخ لك وين.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "يا زمن", text: "يا زمن كافي ظلم، وتجريح،\nترا القلوب ملت، من كثر الوجع.<br>
                        الطيب صار، مذموم،\nوالظالم، هو اللي يرتفع.<br>
                        وين العدالة؟ وين الحق؟\nصار الوطن، مكان للذبح.<br>
                        لكن أبد، ما نستسلم،\nحتى لو صارت، حياتنا كلها مطمع.", genres: ["social-wisdom", "bold-patriotic", "sad-melancholy"] },
                    { title: "الغدر طبعهم", text: "الغدر طبعهم، ما يتغيرون،\nمهما تعاملهم، يظل الغدر بيهم.<br>
                        والوفا كلمة، ما يعرفوها،\nوالعهد عندهم، يبيعونه ويرمون.<br>
                        يا گلبي لا تحزن عليهم،\nترا اللي باعوك، ما يستاهلون.<br>
                        عيش لنفسك، وارفع راسك،\nترا الدنيا، ما تدوم لأحد.", genres: ["betrayal-separation", "social-wisdom"] },
                    { title: "حبك أمل", text: "حبك أمل، في دنيا قاسية،\nيا نور عيني، يا أجمل وعد.<br>
                        كل لحظة وياك، جنة،\nوكل كلمة منك، تزيدني عمد.<br>
                        أنا بلياك، ما أگدر أعيش،\nروحي معلقة، بيك يا سند.<br>
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل الأبد.", genres: ["love-romantic"] },
                    { title: "من همومي", text: "من همومي، گلبي صار صخر،\nوالضحك غاب، ودمعي يجري.<br>
                        كل يوم أسمع، حچي جديد،\nوالروح تتعب، من هذا السهر.<br>
                        يا ليتني، ما عرفت الدنيا،\nولا شفت، منها هذا القهر.<br>
                        لكن أبد، ما أنساك،\nيا جرح گلبي، يا ضوى القمر.", genres: ["sad-melancholy"] },
                    { title: "صرخة وطن", text: "صرخة وطن، تدوي في الأرجاء،\nمن ظلم طاغية، ومن الأعداء.<br>
                        الشعب يصرخ، يريد الحرية،\nوالظلم يزداد، بغير انتهاء.<br>
                        يا رب، خلصنا من الظلم،\nوارفع عنّا، هذا البلاء.<br>
                        العراق يستاهل، كل خير،\nيا رب، ارزقنا، الفرج والرخاء.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "العهد الباطل", text: "العهد الباطل، ما يظل،\nوالكذب حبله، دوم قصير.<br>
                        لا تثق بوعود، كاذبة،\nترا كل كلمة، ما بيها ضمير.<br>
                        عيش بصدقك، وبوفاك،\nترا هو اللي يظل، وما يطير.<br>
                        واللي يخونك، اتركه،\nترا ما يستاهل، أي تقدير.", genres: ["social-wisdom", "betrayal-separation"] }
                ]
            },
            "raheem-almaliki": {
                name: "رحيم المالكي",
                poems: [
                    { title: "مشت روحي", text: "مشت روحي وعفتها بيدك،\nعساني ما مشيت خطوة بلياك.\nكل درب أمشي، أحس خطواتي وياك،\nوكل دگة بگلبي تنادي باسمك.\nيا عيني لا تبچين بعد،\nترا الدمع يخلص ويظل الجرح.\nأنا الما گدرت أعيش بلياك،\nروحي تطلع مني لو شفتك.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "شلت روحي", text: "شلت روحي، وديتها يمك،\nوقلتلك يا حبيبي، هذا قدري.\nرديتها، مجروحة، مكسورة،\nوصرت ما أريد أعيش، ولا أدري.\nالخيانة طعنت گلبي،\nوالموت صار، أحسنلي وأجدرِ.\nيا دنيا كافي عذاب،\nترا القلوب ملت، من كثر الصبر.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "أنا المذنب", text: "أنا المذنب، وأنا اللي أخطيت،\nوعلى خطاي، أتندم ألف مرة.\nما چنت أدري، إن الحب يروح،\nوإن الوفا، ما عنده أي جرة.\nسامحني يا حبيبي، سامحني،\nترا گلبي، ما يحتمل مرة.\nأنا بلياك، ما أگدر أعيش،\nروحي ذبلت، مثل الوردة اللي بتبكي.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "دروب الحياة", text: "دروب الحياة، كلها صعاب،\nواللي يوكف بيها، هو اللي يربح.\nلا تستسلم، للمشاكل،\nترا كل صعب، يجي بعده الفرج.\nعيش بقوة، وبروح صلبة،\nترا الضعف، ما يجيبلك أي ربح.\nخليك ذيب، بين الذئاب،\nحتى تظل، فوق الجميع، وتفرح.", genres: ["social-wisdom"] },
                    { title: "قلبي يبكي", text: "قلبي يبكي، ودموعي تنزل،\nعلى ولف راح، وما يدري بحالي.<br>
                        يا ليتني، ما عرفت الحب،\nولا شفت منك، هذا الهلاك.<br>
                        الوفا مات، في زماننا،\nوالخيانة طبع، بأهل العناد.<br>
                        يا دنيا كافي، ظلم وعذاب،\nترا روحي، ملت، من هذا الوداع.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا حبي الأول", text: "يا حبي الأول، يا نصفي الثاني،\nيا شمس عمري، يا أجمل غرام.\nمن يوم اللي شفتك، تغيرت حياتي،\nوصرت ما أفكر، بغيرك ولا أنام.<br>
                        أنت الروح، وأنت القلب،\nوأنت اللي في عيني، أعلى مقام.<br>
                        أنا بلياك، ما أگدر أعيش،\nترا روحي، تشتاق، كل عام.", genres: ["love-romantic"] },
                    { title: "الخاين", text: "الخاين، ما عنده ضمير،\nولا عنده، أي وفاء.\nيبيع روحه، لأجل الفلوس،\nويترك اللي يحبه، ويختار الجفاء.<br>
                        يا ليتني، ما شفتك،\nولا عرفت، معنى الشقاء.<br>
                        ترا اللي يغدر، ما يربح،\nوعاقبته، تكون، هي الفناء.", genres: ["betrayal-separation", "social-wisdom"] },
                    { title: "صمت الليل", text: "صمت الليل، يحكي همومي،\nوالنجوم تشهد، على ألمي.\nيا دنيا، كافي عذاب،\nترا روحي، تعبت، من هذا الهم.<br>
                        أنا اللي ضحيت، لأجلهم،\nوهم باعوني، بأرخص الثمن.<br>
                        لكن أبد، ما أنسى،\nاللي خانني، واللي ظلمني.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا وطني", text: "يا وطني، يا عشگي الأول،\nيا دجلة والفرات، يا أغلى ما عندي.<br>\nبدمي أرويك، وبعيني أحميك،\nولأجلك، أفدي روحي، وبكل جهدي.<br>\nالتاريخ يشهد، على أصالتنا،\nوالشجاعة طبعنا، وما بيها تردد.<br>\nسنبقى أوفياء، لترابك،\nيا عراق، يا وطن، يا نبض گلبي.", genres: ["bold-patriotic"] },
                    { title: "نصيحة العمر", text: "نصيحة العمر، لا تثق بسهولة،\nترا الناس أصناف، بيها الخير والشر.<br>\nواللي يقولك، أنا وفي،\nترا الكذب، يجري في دمه مثل النهر.<br>\nعيش لضميرك، ولربك،\nترا هو اللي يظل، وما يتغير.<br>\nواللي يغدر، اتركه،\nترا ما يستاهل، أي عمر.", genres: ["social-wisdom", "betrayal-separation"] }
                ]
            },
            "abd-alhussein-alhalfy": {
                name: "عبد الحسين الحلفي",
                poems: [
                    { title: "يا گلبي", text: "يا گلبي شبيك ما ترتاح؟\nمن كثر الهموم والحزن.\nأنا اللي گضيت عمري حسرات،\nوالفرح ما مر بيه ولا يوم.\nيا دنيتي كافي عذاب،\nروحي ملت من كثر الآهات.\nبس الصبر بگلبي ظل،\nأنتظر الفرج، يا رب.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "مرارة الحب", text: "مرارة الحب، تقتل الروح،\nإذا كان الحب، ما بيه وفاء.\nيا ليتني ما عرفت الحب،\nولا شفت منه، هذا العناء.<br>\nالقلب ينزف، والدمع يجري،\nعلى ولف خان، وما عنده حياء.<br>\nيا دنيا، كافي جروح،\nترا روحي، ملت، من الشقاء.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "دموع القدر", text: "دموع القدر، تجري بلا صوت،\nعلى أحلام ضاعت، وما ترجع.<br>\nالوفا مات، في قلوب الناس،\nوالخيانة طبعهم، ما تنفع.<br>\nيا ليتني، ما وثقت بأحد،\nولا عرفت، معنى الوجع.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي نفع.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الأيام دول", text: "الأيام دول، يوم الك ويوم عليك،\nواللي يضحكلك اليوم، باچر يبكي.<br>\nلا تثق بالوجوه الزائفة،\nترا وراها، ألف قصة تحكي.<br>\nكن قوياً، واثقاً بنفسك،\nترا الدنيا، ما بيها أي صدق.<br>\nعيش بضميرك، ورفع راسك،\nترا اللي يخانك، ما يستاهل أي حب.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا حلم العمر", text: "يا حلم العمر، يا أغلى وعد،\nيا شمس عمري، يا أحلى بلد.<br>\nكل دگة بگلبي، تنادي باسمك،\nوكل لحظة بلياك، ما الها أي حد.<br>\nأنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى سند.<br>\nأنا بلياك، ما أگدر أعيش،\nيا حبيبي، يا كل الأبد.", genres: ["love-romantic"] },
                    { title: "الوفا قليل", text: "الوفا قليل، والقلوب غدارة،\nوالصدق نادر، في هذا الزمن.<br>\nالناس تدور، على مصلحتها،\nوالعهد، ما عنده أي ثمن.<br>\nيا ليتني، ما عرفت الدنيا،\nولا شفت منها، هذا الوهن.<br>\nلكن أبد، ما أنسى،\nاللي خانني، واللي طعن.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "قصة حزن", text: "قصة حزن، عاشتها روحي،\nوالدمع يجري، على الخدين.<br>\nعلى ولف راح، وما رجع،\nوتركني وحدي، بين نارين.<br>\nيا ليل، كافي هموم،\nترا گلبي، ما يحتمل بعدين.<br>\nأريد أرتاح، أريد أنام،\nوأنسى كلشي، وأنسى السنين.", genres: ["sad-melancholy"] },
                    { title: "رسالة حب", text: "رسالة حب، أرسلها إلك،\nيا أغلى انسان، يا كل دنيتي.<br>\nأحبك حباً، ما يوصفه كلام،\nيا شمس عمري، يا كل أمنيتي.<br>\nعيوني تسهر، وتناطر جيتك،\nوروحي تفرح، لو شفتك يا غايتي.<br>\nتبقى بگلبي، طول العمر،\nيا حبيبي، يا كل سعادتي.", genres: ["love-romantic"] },
                    { title: "مصير الظالم", text: "مصير الظالم، نهايته تكون،\nوالحق يظهر، مهما طال الزمن.<br>\nلا تفرح، بظلمك يا طاغي،\nفالله يرى، وهو الحكم.<br>\nالشعب أقوى، من كل ظالم،\nورايته عالية، ما تنحني أبد.<br>\nيا عراق، سنبقى أوفياء،\nولأجلك، نفدي الأرواح، والجسد.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "مرارة الخيانة", text: "مرارة الخيانة، تكسر الروح،\nوتخلي القلب، يعيش في عذاب.<br>\nمن كثر ما شفت، من غدر،\nصرت أخاف، حتى من الأحباب.<br>\nيا دنيا، كافي درس،\nترا روحي، ملت، من هذا العتاب.<br>\nلكن أبد، ما أنسى،\nكل واحد خان، ولف لي كتاب.", genres: ["betrayal-separation", "sad-melancholy"] }
                ]
            },
            "ahmed-matar": { // Though more classical/political, snippets can fit social/bold
                name: "أحمد مطر",
                poems: [
                    { title: "نحن باقون", text: "نحن باقون... والأسماء قد تتغير،\nلكن وجه العدو لا يتغير.\nنحن صوت الأرض، صوت الشعب،\nمن تحت الركام، من لهيب النار.\nلا تظنوا أننا قد متنا،\nفنحن الشجر الذي لا يموت.\nكلما قطعوا منا غصناً،\nنبتت آلاف الأغصان من جديد.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "لا تشتروا العز", text: "لا تشتروا العز ببيع الأرض،\nفالبيع بيع الروح، بيع الشرف.\nالوطن ليس سوقاً للمساومة،\nولا سلعة تباع وتشترى.\nحافظوا عليه، فهو دمكم،\nفهو شرفكم، وهو عزكم.\nفلا قيمة لأرض تبيعونها،\nإذا ما ضاع فيها العز والحرف.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "فلسطين", text: "فلسطين، يا جرح الأمة،\nيا صرخة الحق، في وجه الظلام.<br>\nمتى تعودين، حرة أبية،\nويرفرف علمك، في كل مكان.<br>\nيا شعب العزم، لا تيأس،\nفالنصر قادم، بعد هذا الآلام.<br>\nسنحررك، بأرواحنا،\nيا فلسطين، يا أغلى الأوطان.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "الكلمة", text: "الكلمة، سيف، إذا كانت حقاً،\nوسم، إذا كانت كذباً وزوراً.\nلا تخافوا، من قول الحق،\nفالحق هو الذي، ينتصر ويثور.<br>\nالصمت، موت، في زمن الظلم،\nوالسكوت، يزيدنا، قهراً وجوراً.\nكونوا صوتاً، لا يخشى،\nحتى لو كان، وحده، هو المكسور.", genres: ["social-wisdom", "bold-patriotic"] },
                    { title: "منفى الروح", text: "منفى الروح، في جسد الوطن،\nوالغرباء يحكمون، هذا الزمن.\nالظلم يزداد، والعدل غاب،\nوالشعب يعاني، من كثر المحن.<br>\nيا ليتني، كنت طيراً،\nلأطير بعيداً، عن هذا الحزن.\nلكن روحي، في هذا التراب،\nوستبقى، مهما طال، هذا الكفن.", genres: ["sad-melancholy", "bold-patriotic"] },
                    { title: "يا دمي", text: "يا دمي، لا تخن وطني،\nفالخيانة، هي أقسى الذنوب.<br>\nكن وفياً، حتى الممات،\nفالوفا، هو أسمى الدروب.<br>\nلا تبيع، ضميرك،\nفالضمير، هو الذي لا يغيب.<br>\nعش حراً، مت مرفوع الرأس،\nترا الدنيا، ما بيها أي مكروه.", genres: ["bold-patriotic", "social-wisdom", "betrayal-separation"] },
                    { title: "رسالة إلى حاكم", text: "رسالة إلى حاكم، لا يرى،\nأن الشعب، هو الأساس.\nالظلم ما يدوم، والباطل يزول،\nفالنار، تأكل، كل أساس.<br>\nاتق الله، في شعبك،\nفالله يرى، وهو خير الناس.<br>\nالتاريخ لا يرحم،\nوكل ظالم، نهايته، في الهلاك.", genres: ["bold-patriotic", "social-wisdom"] },
                    { title: "الأرض تتكلم", text: "الأرض تتكلم، بصوت الشهداء،\nوالدم يروي، قصة العناء.<br>\nلا تسألوا، لماذا نحزن،\nفالحزن يملأ، كل الأجواء.<br>\nالعراق يبكي، على أولاده،\nوالأعداء، يزيدون، هذا البلاء.<br>\nيا رب، خلصنا من الظلم،\nوانصرنا، على الأعداء.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "الحرية", text: "الحرية، ليست كلمة،\nبل هي، دم وروح، وعرق جبين.<br>\nلا تبيعها، بأي ثمن،\nفالعبودية، هي أقسى سكين.<br>\nناضل، حتى آخر رمق،\nفالنصر، يأتي، للصامدين.<br>\nالعراق، يناديكم،\nكونوا له، خير معين.", genres: ["bold-patriotic"] },
                    { title: "وصية", text: "وصية مني، إلى كل عربي،\nلا تبيع، أرضك، لا تبيع كرامتك.\nفالعزة، أغلى من الدنيا،\nوالحرية، هي طريق حياتك.<br>\nلا تيأس، من رحمة الله،\nفهو القادر، على نجاتك.\nفالعراق، باقٍ،\nوستعود، أمجادك.", genres: ["social-wisdom", "bold-patriotic"] }
                ]
            },
            "saheb-aldawiri": {
                name: "صاحب الضويري",
                poems: [
                    { title: "بگت روحي", text: "بگت روحي ودمعي يجرن عليك،\nيا ليل الشوگ، شسويت بيّه.\nأنا بلياك وردة ذبلت،\nوالگلب من فرگاك مليته.\nترد الروح لو ردّيت،\nوكل فرحة تجي لو شفتك.\nيا أغلى من روحي، يا كل عمري،\nشگد مشتاگ لشوفتك يا حبيبي.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "يا دمعة العين", text: "يا دمعة العين، لا توگفين،\nعلى ولف راح، وما يدري بحالي.\nالروح ملت، من كثر الونين،\nوالقلب مجروح، ما يطيب تالي.\nيا ليتني، ما عرفت الحب،\nولا شفت منه، هذا الهلاك.\nالدنيا ظالمة، ما بيها رحمة،\nوالحزن ساكن، في كل ليالي.", genres: ["sad-melancholy"] },
                    { title: "حسابات الأيام", text: "حسابات الأيام، ما تنتهي،\nوكل يوم يمر، يزيدني تعب.\nالوفا صعب، تلاگيه،\nوالخيانة طبع، بأهل الكذب.\nيا گلبي، لا تتعجب،\nترا الدنيا، ما بيها أي عجب.<br>\nعيش لنفسك، واترك الماضي،\nترا اللي خانك، ما يستاهل أي حب.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "عهد الحب", text: "عهد الحب، يبقى بگلبي،\nمهما طال الزمان، أو قصر.<br>
                        أحبك حباً، ما يوصفه كلام،\nيا شمس عمري، يا أحلى قمر.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "طعنة الظهر", text: "طعنة الظهر، أشد من السيف،\nتكسر القلب، وما تخليه يطيب.<br>\nمن أقرب الناس، جاني الغدر،\nوالوفا منهم، صار بس كذب.<br>\nيا ليتني، ما وثقت بأحد،\nولا شفت منهم، هذا العذيب.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي حبيب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "حكم الأيام", text: "حكم الأيام، ما يتغير،\nواللي يضحك، باچر يبكي.<br>\nلا تفرح، بمالك،\nترا الفلوس، ما تدوم، وما تبقى.<br>\nعيش بصدقك، وبضميرك،\nترا هو اللي ينفعك، ويبقى.<br>\nواللي يغدر، اتركه،\nترا ما يستاهل، أي كلمة.", genres: ["social-wisdom"] },
                    { title: "دموع الفراق", text: "دموع الفراق، سالت مثل المطر،\nعلى ولف راح، وما يدري بالقهر.<br>
                        يا ليتني، ما عرفت الوداع،\nولا شفت منه، هذا العذاب.<br>
                        القلب ينزف، والروح تصرخ،\nعلى حب ضاع، وصار بس سراب.<br>
                        يا دنيا، كافي جروح،\nترا روحي، ملت، من هذا العذاب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الوفا طبعي", text: "الوفا طبعي، ما أغيره،\nحتى لو خانتني، كل الناس.<br>\nأنا اللي أوفي، بكلمتي،\nوما أبيع، ضميري، بأي إحساس.<br>\nفليخونوا، ما يهمني،\nترا ربي، هو اللي يحاسب الناس.<br>\nواللي يقدرني، أقدره،\nواللي يخونني، ما عليه أي حراس.", genres: ["social-wisdom"] },
                    { title: "أحبك", text: "أحبك، كلمة، ما تكفيك،\nفحبي أكبر، من كل الكلام.<br>\nأنت الروح، وأنت القلب،\nوأنت اللي في عيني، أعلى مقام.<br>\nكل لحظة بدونك، عذاب،\nوكل دقيقة، تمر كأنها ألف عام.<br>\nيا شمس عمري، يا ضوى أيامي،\nتظل بگلبي، حتى في الأحلام.", genres: ["love-romantic"] },
                    { title: "الندم", text: "الندم، شعور، يقتل الروح،\nإذا فات الأوان، وما ينفع الندم.<br>\nلا تتهور، ولا تندفع،\nفالعواقب، تكون، هي الألم.<br>\nفكر زين، قبل لا تتكلم،\nفالكلمة، سيف، إذا كانت غلط.<br>\nواللي يغلط، يندم،\nوكل غلطة، الها حساب، في العظم.", genres: ["social-wisdom"] }
                ]
            },
            "ehab-almaliki": {
                name: "إيهاب المالكي",
                poems: [
                    { title: "خلص كلشي", text: "خلص كلشي بلياك، والوكت راح،\nوبقت روحي الك، ما تريد سواك.\nأنا اللي تعبت من كثر البچي،\nوالعين ما شافت غيرك إنت.\nيا گلبي لا تلومني على حبي،\nهذا هو العشگ، مو بيدي ولا بيدك.\nبس الحسرة بگلبي، ما تروح،\nوالدمعة بعيني، ما تنشف ابد.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "يا نصفي الثاني", text: "يا نصفي الثاني، يا كل دنيتي،\nيا شمس عمري، يا أجمل وعد.<br>\nحبك بگلبي، يروي سنيني،\nوغيرك أبد، ما أحب ولا أرتعد.<br>\nأنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى سند.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.", genres: ["love-romantic"] },
                    { title: "خيانة الأقرباء", text: "خيانة الأقرباء، أصعب خيانة،\nتكسر القلب، وما تخليه يطيب.<br>\nمن اللي كنت أثق بيهم،\nجاني الغدر، وعيشني العذيب.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منهم، هذا الهلاك.<br>\nالوفا مات، في قلوبهم،\nوالغدر يجري، في كل حبيب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "كلمات من القلب", text: "كلمات من القلب، أكتبها إلك،\nيا أغلى من روحي، يا كل العمر.\nأحبك حباً، لا يوصفه كلام،\nيا شمس الدنيا، يا أحلى قمر.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "ألم الفراق", text: "ألم الفراق، يقطع الروح،\nويخلي القلب، يعيش في عذاب.<br>\nمن يوم اللي رحت، ما شفت راحة،\nوالدمع يجري، على الخدود، مثل السحاب.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا العتاب.<br>\nصرت عايش، على الذكريات،\nوالروح تصرخ، من كثر الغياب.", genres: ["sad-melancholy"] },
                    { title: "حكمة العمر", text: "حكمة العمر، لا تثق بوعود،\nتراها تتغير، مع كل ظروف.<br>\nواللي يبيعك، باعه،\nلا تعتب عليه، ولا تقول ظروف.<br>\nعيش لنفسك، ولضميرك،\nفالضمير، هو اللي يبقى، وما يخون.<br>\nواللي يقدرك، هو اللي يستاهل،\nواللي يغدر، ما يستاهل أي حروف.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا وطني يا غالي", text: "يا وطني يا غالي، يا تراب الذهب،\nيا دجلة والفرات، يا روح العرب.\nبدمي أرويك، وبعيني أحميك،\nولأجلك، أقاتل، ضد كل حرب.<br>\nالتاريخ يشهد، على أصالتنا،\nوالشجاعة طبعنا، ما بيها أي كذب.<br>\nسنبقى سادة، ونرفع رايتنا،\nيا عراق، يا أغلى، يا كل الحب.", genres: ["bold-patriotic"] },
                    { title: "ليالي الشوق", text: "ليالي الشوق، تسهر عيوني،\nوالنوم غاب، من كثر التفكير.<br>\nعلى ولف راح، وما يدري بحالي،\nوالقلب مجروح، ما يرضى يطيب.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا المصير.<br>\nصرت عايش، بليلي ونهاري،\nمثل الغريب، اللي ما عنده أي مصير.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "وفاء الروح", text: "وفاء الروح، ما يتغير،\nمهما طالت الأيام، أو قصرت.<br>\nأنا اللي أوفي، بكلمتي،\nحتى لو، كل الناس، تغيرت.<br>\nالحب الصادق، يبقى بگلبي،\nوغيرك أبد، ما حبيت ولا عشقت.<br>\nيا شمس عمري، يا ضوى سنيني،\nتظل بگلبي، حتى لو، أنت، اختفيت.", genres: ["love-romantic"] },
                    { title: "الغدر", text: "الغدر، سكين، يطعن الروح،\nويترك القلب، يعيش في ظلام.<br>\nمن اللي كنت أثق بيهم،\nجاني الطعن، من أهل الذمام.<br>\nيا ليتني، ما عرفت الدنيا،\nولا شفت، منها، هذا الأوهام.<br>\nلكن أبد، ما أنسى،\nاللي غدرني، في هذا العذاب.", genres: ["betrayal-separation", "sad-melancholy"] }
                ]
            },
            "mohammad-alghabban": {
                name: "محمد الغبّان",
                poems: [
                    { title: "عصفور باليد", text: "عصفور باليد، أحسن من عشره على الشجر،\nوهذا مثل يگولونه، يا ناس، بگلبي.<br>\nلا تركض ورا السراب، تتعب،\nوخليك قنوع باللي موجود عندك.\nالدنيا ما بيها أمان، تتغير كل يوم،\nواللي يبيعك، باعه، لا تشتريه.\nاحفظ نفسك من الشرور،\nوعيش بسلام، ويا رب.", genres: ["social-wisdom"] },
                    { title: "جروح الغدر", text: "جروح الغدر، ما تلتئم بسهولة،\nتترك آثار، في القلب، ما تروح.<br>\nمن اللي كنت أثق بيهم،\nجاني الطعن، وخلاني، في الجروح.<br>\nيا ليتني، ما عرفت الدنيا،\nولا شفت منها، هذا الوجوه.<br>\nلكن أبد، ما أنسى،\nاللي خانني، واللي تركني وحدي.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "يا ناس", text: "يا ناس، كافي ظلم،\nترا القلوب، ملت، من هذا العذاب.<br>\nالفقير يموت، من الجوع،\nوالغني، عايش، في أطيب الثياب.<br>\nوين العدالة؟ وين الحق؟\nصار الوطن، مثل بيت خراب.<br>\nيا رب، خلصنا من الظلم،\nوارزقنا، الفرج، يا وهاب.", genres: ["social-wisdom", "bold-patriotic", "sad-melancholy"] },
                    { title: "حب بلا حدود", text: "حب بلا حدود، أقدمه إلك،\nيا أغلى من روحي، يا كل العمر.\nأنت النبض، وأنت الروح،\nوأنت اللي في عيني، أحلى قدر.<br>\nكل لحظة وياك، جنة،\nوكل دقيقة، تمر، مثل العطر.<br>\nأنا بلياك، ما أگدر أعيش،\nيا حبيبي، يا أجمل قمر.", genres: ["love-romantic"] },
                    { title: "ألم الوداع", text: "ألم الوداع، يكسر الروح،\nويخلي القلب، يعيش في عذاب.<br>\nمن يوم اللي رحت، ما شفت راحة،\nوالدمع يجري، على الخدود، مثل السحاب.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا العتاب.<br>\nصرت عايش، على الذكريات،\nوالروح تصرخ، من كثر الغياب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الصديق الخائن", text: "الصديق الخائن، لا تثق بيه،\nترا الغدر طبعهم، ما يتغيرون.<br>\nيضحك بوجهك، ويطعنك بالظهر،\nوبلحظة، ينسى، كل اللي كان.<br>\nيا ليتني، ما وثقت بأحد،\nولا شفت منهم، هذا الهوان.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي أمان.", genres: ["betrayal-separation", "social-wisdom"] },
                    { title: "يا شمس الحب", text: "يا شمس الحب، لا تغيبين،\nفغيابك، يطفئ، كل الأنوار.<br>\nأنت النور، الذي يضيء دربي،\nوأنت الأمل، في كل الأقدار.<br>\nأنا بلياك، مثل وردة ذبلت،\nوالروح تبكي، من كثر الأمرار.<br>\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل الأسرار.", genres: ["love-romantic"] },
                    { title: "ظلم الدنيا", text: "ظلم الدنيا، ما ينتهي،\nوالناس تتغير، مع كل زمن.<br>\nاللي تحبه اليوم، باچر يروح،\nواللي توثق بيه، يطعنك في الكفن.<br>\nيا رب، خلصنا من الظلم،\nوارزقنا، السلام، والأمن.<br>\nترا القلوب، ملت،\nمن هذا العذاب، وهذا الوهن.", genres: ["social-wisdom", "sad-melancholy"] },
                    { title: "الوفا والصداقة", text: "الوفا والصداقة، كنز،\nما تلاگيه، في كل مكان.<br>\nحافظ عليه، ولا تبيعه،\nفالوفي، هو اللي يظل، طول الزمان.<br>\nوالصديق الصادق، نعمة،\nمن رب العباد، يا إنسان.<br>\nلا تفرط بيه، ولا تخسره،\nترا الصديق، سندك، في كل الأزمان.", genres: ["social-wisdom"] },
                    { title: "صرخة حرة", text: "صرخة حرة، في وجه الظلام،\nمن شعب يريد، يعيش بسلام.<br>\nلا ينحني، ولا يخضع،\nويرفع راسه، في كل مقام.<br>\nيا عراق، يا أغلى وطن،\nسنبقى نحميك، حتى المنام.<br>\nلا تخاف، من أي عدو،\nفالنصر قادم، وسترتفع الأعلام.", genres: ["bold-patriotic"] }
                ]
            },
            "ali-almansouri": {
                name: "علي المنصوري",
                poems: [
                    { title: "حسابات العمر", text: "حسابات العمر، كلها خسارة،\nإذا ما چنت وياك، يا أغلى البشر.\nكل لحظة بدونك، عذاب،\nوكل دقيقة تمر، مثل الجمر.\nيا شمسي، يا ضوى عيني،\nأنا بلياك، ما أگدر أسهر.\nتظل بگلبي، طول العمر،\nيا حبيبي، يا أجمل قدر.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "طول غيابك", text: "طول غيابك، وجفاني النوم،\nوالعين سهرت، من كثر الهموم.<br>\nالروح ملت، من كثر الونين،\nوالقلب مجروح، ما يطيب بيوم.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منك، ذاك اللوم.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي معلوم.", genres: ["sad-melancholy"] },
                    { title: "درس الوفاء", text: "درس الوفاء، تعلمته منك،\nيا من كنت، لي خير صديق.<br>\nالوفا طبعك، والصدق دربك،\nوغدرك أبد، ما عرف طريق.<br>\nأنا اللي أوفي، بكلمتي،\nحتى لو كان، الدرب ضيق.<br>\nتظل بگلبي، طول العمر،\nيا وفي، يا خير رفيق.", genres: ["social-wisdom"] },
                    { title: "خيّب ظني", text: "خيّب ظني، اللي كنت أحبه،\nوطعن گلبي، بأقسى سكين.<br>\nباع الوفا، بأرخص الأثمان،\nوتركني وحدي، بين نارين.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منه، هذا الغدر.<br>\nصرت عايش، على الذكريات،\nوالروح تبكي، من كثر القهر.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "نار الشوق", text: "نار الشوق، تحرگ بگلبي،\nوالروح تصرخ، من كثر الحنين.<br>\nيا ليتني، يمك، أضمك،\nوأنسى كلشي، وأنسى السنين.<br>\nأنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى زين.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، يا أجمل عين.", genres: ["love-romantic"] },
                    { title: "حياة الفقير", text: "حياة الفقير، كلها آلام،\nوهموم الدنيا، تزيدها ظلام.<br>\nلا أحد يسمع، ولا أحد يرى،\nوكل واحد، عايش، في أوهام.<br>\nيا رب، ارحم، بحالهم،\nوارزقهم، السلام، والأمان.<br>\nفالفقر، يقتل، الأرواح،\nويخلي، القلوب، تعيش في حسرة.", genres: ["social-wisdom", "sad-melancholy"] },
                    { title: "وداعاً يا حب", text: "وداعاً يا حب، يا كل الأوهام،\nفقد مت، في قلبي، كل غرام.<br>\nالخيانة طبعك، والغدر سيفك،\nوالموت، أرحم، من هذا الظلام.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منك، هذا الهيام.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي سلام.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "ابتسامة أمل", text: "ابتسامة أمل، في زمن الحزن،\nتضيء الدروب، في كل محن.<br>\nلا تيأس، من رحمة الله،\nفهو القادر، على كل زمن.<br>\nعيش بقوة، وبروح صلبة،\nترا الله وياك، مهما يكون.<br>\nواللي يحبك، يظل وياك،\nواللي يبيعك، ما يستاهل أي ثمن.", genres: ["social-wisdom"] },
                    { title: "يا وطني يا دمي", text: "يا وطني يا دمي، يا روحي،\nيا أغلى من كل، كنوز الدنيا.<br>\nبترابك، روحي، تظل،\nولأجلك، أفدي، كل، سنيني.<br>\nالشجاعة طبعنا، ما نخون،\nوالوفا، دربنا، يا أغلى ما عندي.<br>\nسنبقى، أوفياء، لك،\nيا عراق، يا كل، أمنياتي.", genres: ["bold-patriotic"] },
                    { title: "لحظة ضعف", text: "لحظة ضعف، مرت بيّه،\nخلتني أشكي، همومي لغيري.<br>\nيا ليتني، ما حچيت،\nولا شفت، منهم، هذا التعب.<br>\nالناس ما ترحم،\nوكل واحد، يدور، على نفسه.<br>\nعيش بسلام، وحدك،\nترا العالم، كله، ما بيه، أي نفع.", genres: ["sad-melancholy", "social-wisdom"] }
                ]
            },
            "fallah-aloboodi": {
                name: "فلاح العبودي",
                poems: [
                    { title: "ذكرياتك", text: "ذكرياتك، ما تفارگ بالي،\nوكل لحظة تمر، تزيدني جنون.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منك، ذاك العيون.<br>\nالروح ذبلت، من كثر البچي،\nوالقلب مجروح، ما يرضى يلين.<br>\nيا دنيا، كافي عذاب،\nترا روحي، ملت، من هذا الحنين.", genres: ["sad-melancholy", "love-romantic"] },
                    { title: "حبيبتي", text: "حبيبتي، يا أغلى من روحي،\nيا شمس عمري، يا أجمل قمر.<br>\nأحبك حباً، لا يوصفه كلام،\nيا كل أمنياتي، يا أغلى بشر.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\nتظل بگلبي، طول العمر،\nيا حبيبتي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "الندم المتأخر", text: "الندم المتأخر، ما ينفع،\nإذا فات الأوان، وماكو رجوع.<br>\nالخيانة طبعك، والغدر سيفك،\nوباعتني بأرخص الأثمان، بدون دموع.<br>\nيا ليتني، ما وثقت بأحد،\nولا شفت منك، هذا الخضوع.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي طوع.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "صبر الأيام", text: "صبر الأيام، يعلمك هوايه،\nوالناس أصناف، بيها الخير والشر.<br>\nلا تندم على شي فات،\nترا القدر مكتوب، وما يتغير.<br>\nعيش بسلام، ورفع راسك،\nترا الله وياك، وهو خير البشر.<br>\nواللي يغدر، لا تبالي،\nترا نهايته، تكون، هي القهر.", genres: ["social-wisdom"] },
                    { title: "ليل العشاق", text: "ليل العشاق، ساهر بيك،\nوالنجوم تشهد، على سهر عيني.<br>\nيا ليتني، يمك، أضمك،\nوأنسى كلشي، وأنسى السنين.<br>\nأنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى زين.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، يا أجمل عين.", genres: ["love-romantic"] },
                    { title: "طعنة الغدر", text: "طعنة الغدر، تكسر الروح،\nوتخلي القلب، يعيش في عذاب.<br>\nمن أقرب الناس، جاني الطعن،\nوخلاني، وحيد، بين الصحاب.<br>\nيا ليتني، ما وثقت بأحد،\nولا شفت، منهم، هذا العتاب.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي أحباب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "يا وطني يا روحي", text: "يا وطني يا روحي، يا كل عمري،\nيا أغلى من كنوز الدنيا.\nبترابك، روحي، تظل،\nولأجلك، أفدي، كل سنيني.<br>\nالشجاعة طبعنا، ما نخون،\nوالوفا، دربنا، يا أغلى ما عندي.<br>\nسنبقى، أوفياء، لك،\nيا عراق، يا كل أمنياتي.", genres: ["bold-patriotic"] },
                    { title: "الحكمة في الحياة", text: "الحكمة في الحياة، تگول،\nلا تركض ورا السراب، تتعب.\nاختار طريقك، بعناية،\nترا الدنيا، كلها، مو بس لعب.\nالصديق الصادق، كنز،\nوالخاين، ما عنده، أي كذب.<br>\nعيش بضميرك، ورفع راسك،\nترا الله، وياك، وهو، اللي يكتب.", genres: ["social-wisdom"] },
                    { title: "دموع القدر", text: "دموع القدر، تجري بلا صوت،\nعلى أحلام ضاعت، وما ترجع.<br>\nالوفا مات، في قلوب الناس،\nوالخيانة طبعهم، ما تنفع.<br>\nيا ليتني، ما وثقت بأحد،\nولا عرفت، معنى الوجع.<br>\nأعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي نفع.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "أحبك يا وطن", text: "أحبك يا وطن، يا دجلة والفرات،\nيا أرض النخيل، يا أغلى التراب.<br>\nبدمي أرويك، وبعيني أحميك،\nولأجلك، أقاتل، ضد كل حراب.<br>\nالشعب العراقي، ما ينكسر،\nولرايته، يظل، مرفوع الرأس.<br>\nسنبني العراق، من جديد،\nونرفع رايته، بين كل الناس.", genres: ["bold-patriotic"] }
                ]
            },
            "hussein-ali-almatouri": {
                name: "حسين علي المطوري",
                poems: [
                    { title: "يا وردة", text: "يا وردة، يا عطر، يا روح،\nيا كلشي حلو، في هذا الوجود.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\nعيوني تسهر، وتناطر جيتك،\nوالقلب ينبض، بس باسمك يا ودود.<br>\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل الحدود.", genres: ["love-romantic"] },
                    { title: "بعدك يوجع", text: "بعدك يوجع، والقلب ما يطيب،\nوالروح تبكي، من كثر الدموع.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منك، هذا الخضوع.<br>\nالخيانة طعنت، في ظهري،\nوخلتني، عايش، بين الجروح.<br>\nيا دنيا، كافي عذاب،\nترا روحي، ملت، من كثر هذا الوجع.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الحياة أسرار", text: "الحياة أسرار، ما تنتهي،\nوكل يوم، نتعلم، درس جديد.<br>\nلا تثق، بالوجوه الزائفة،\nترا الكذب، طبعهم، وما يفيد.<br>\nعيش بصدقك، وبوفاك،\nترا هو اللي يبقى، وما يروح.<br>\nواللي يخونك، اتركه،\nترا ما يستاهل، أي وعد.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا روح الروح", text: "يا روح الروح، يا كل عمري،\nيا شمس الدنيا، يا أجمل قمر.<br>\nحبك بگلبي، يروي سنيني،\nوغيرك أبد، ما أحب ولا أرتعد.<br>\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "عذاب الحب", text: "عذاب الحب، ما يخلص،\nاذا كان الوفا، ما بيه ضمير.<br>\nالقلب ينزف، والروح تبكي،\nعلى حب ضاع، وماكو مصير.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منه، هذا العذيب.<br>\nصرت عايش، على الذكريات،\nوالروح تصرخ، من كثر التفكير.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "الغيرة", text: "الغيرة نار، تحرگ الروح،\nوتخلي القلب، يعيش في عذاب.<br>\nيا ليتني، ما عرفت الحب،\nولا شفت منك، هذا العذاب.<br>\nالوفا مات، في زماننا،\nوالخيانة طبع، بأهل الكذاب.<br>\nيا دنيا، كافي جروح،\nترا روحي، ملت، من هذا العتاب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا وطني", text: "يا وطني، يا عشقي الأول،\nيا دجلة والفرات، يا أغلى ما عندي.<br>\nبدمي أرويك، وبعيني أحميك،\nولأجلك، أفدي روحي، وبكل جهدي.<br>\nالتاريخ يشهد، على أصالتنا،\nوالشجاعة طبعنا، ما بيها تردد.<br>\nسنبقى أوفياء، لترابك،\nيا عراق، يا وطن، يا نبض گلبي.", genres: ["bold-patriotic"] },
                    { title: "الحياة مدرسة", text: "الحياة مدرسة، تعلمك هوايه،\nوالزمن يثبتلك، كل شي جديد.<br>\nلا تندم على شي فات،\nوعيش يومك، وسوي اللي يفيد.<br>\nالصديق الصادق، كنز،\nوالخاين، ما عنده، أي كذب.<br>\nعيش بضميرك، ورفع راسك،\nترا الله، وياك، وهو، اللي يكتب.", genres: ["social-wisdom"] },
                    { title: "دموع الوفاء", text: "دموع الوفاء، سالت مثل النهر،\nعلى ولف راح، وما يدري بالقهر.<br>\
                        الروح تبكي، والقلب ينزف،\nعلى حب ضاع، وما رجع بعد.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت منك، هذا الغدر.<br>\
                        أعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي بشر.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا حبي الأبدي", text: "يا حبي الأبدي، يا نور عيني،\nيا شمس عمري، يا أجمل وعد.<br>\
                        كل لحظة وياك، جنة،\nوكل دقيقة، تمر، مثل العطر.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic"] }
                ]
            },
            "raed-abufetyan": {
                name: "رائد ابو فتيان",
                poems: [
                    { title: "الخلگ مالت ناس", text: "الخلگ مالت ناس، بس روحي إلك،\nوكل دگة بگلبي، تنادي باسمك.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        يا حبيبي، يا كل عمري،\nيا شمس الدنيا، يا أحلى وعد.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل الأبد.", genres: ["love-romantic"] },
                    { title: "صفحة الماضي", text: "صفحة الماضي، طويتها،\nوعشت لحالي، بدونك يا خوان.<br>\
                        الخيانة طبعك، والغدر سيفك،\nوالوفا منك، ما بيه أي أمان.<br>\
                        يا ليتني، ما وثقت بأحد،\nولا شفت منك، هذا الهوان.<br>\
                        أعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي إنسان.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "درس من الماضي", text: "درس من الماضي، تعلمته،\nالطيب ما ينفع، مع كل البشر.<br>\
                        بعض البشر، ما يقدرون،\nوالوفا عندهم، أغلى من الدرر.<br>\
                        عيش لنفسك، واترك الماضي،\nترا اللي خانك، ما يستاهل العذر.<br>\
                        عيش بسلام، ورفع راسك،\nترا العمر قصير، لا تضيعه بالقهر.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا گلبي", text: "يا گلبي شبيك ما ترتاح؟\nمن كثر الهموم والحزن.\nأنا اللي گضيت عمري حسرات،\nوالفرح ما مر بيه ولا يوم.<br>\
                        يا دنيتي كافي عذاب،\nروحي ملت من كثر الآهات.\nبس الصبر بگلبي ظل،\nأنتظر الفرج، يا رب.", genres: ["sad-melancholy"] },
                    { title: "حبك حلم", text: "حبك حلم، عشت بيه،\nوكل لحظة وياك، جنة.<br>\
                        يا ليتني، ما صحيت،\nولا شفت، منك، هذا العناء.<br>\
                        الروح ذبلت، من كثر البچي،\nوالقلب مجروح، ما يرضى يلين.<br>\
                        يا دنيا، كافي عذاب،\nترا روحي، ملت، من هذا الحنين.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "ألم الخيانة", text: "ألم الخيانة، يكسر الروح،\nويخلي القلب، يعيش في ظلام.<br>\
                        من اللي كنت أثق بيهم،\nجاني الطعن، من أهل الذمام.<br>\
                        يا ليتني، ما عرفت الدنيا،\nولا شفت، منها، هذا الأوهام.<br>\
                        لكن أبد، ما أنسى،\nاللي غدرني، في هذا العذاب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "نصيحة", text: "نصيحة مني، لا تثق بأحد،\nترا الناس تتغير، مع كل زمن.<br>\
                        اليوم صاحبك، باچر عدوك،\nوالأيام تثبتلك، هذا المثل.<br>\
                        عيش لنفسك، ولضميرك،\nولا تسوي شي، يزعجك أبد.<br>\
                        واللي ما يقدرك، اتركه،\nترا الحياة قصيرة، وما بيها نفع.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "صوت الوفاء", text: "صوت الوفاء، ما يموت أبداً،\nيبقى يصدح، في كل مكان.\nيناديكم، يا أبناء وطني،\nحافظوا على الأرض، من الخوان.<br>\
                        لا تسلموا، ذرة تراب،\nفالعراق أمانة، من رب الأكوان.\nسنبقى صامدين، بوجه الأعداء،\nلأجل العراق، نضحي بكل الأثمان.", genres: ["bold-patriotic"] },
                    { title: "عيونك", text: "عيونك، سحرتني،\nوخلتني أعشق، كل ما فيك.<br>\
                        يا أجمل عيون، شفتها،\nأنا بلياك، ما أگدر أعيش.<br>\
                        يا روحي، يا كل عمري،\nتظل بگلبي، ما أقدر أنساك.<br>\
                        يا حبيبي، يا كل الأبد،\nروحي فدوة، لعينيك.", genres: ["love-romantic"] },
                    { title: "هموم الوطن", text: "هموم الوطن، تكسر الروح،\nوالقلب ينزف، من كثر الجروح.<br>\
                        الشعب يعاني، من الظلم،\nوالحزن ساكن، في كل الوجوه.<br>\
                        يا رب، خلصنا من الظلم،\nوارزقنا، الفرج، يا رحيم.<br>\
                        فالعراق يستاهل، كل خير،\nوأهله يستاهلون، أطيب النعيم.", genres: ["bold-patriotic", "sad-melancholy"] }
                ]
            },
            "mohammad-alsari": {
                name: "محمد الساري",
                poems: [
                    { title: "يا روحي لا تبجي", text: "يا روحي لا تبجي على الفات،\nترا الدمع ما يرجع اللي راح.<br>\
                        عشت وياك أيام وسنين،\nوما شفت منك بس الجراح.<br>\
                        خانوا الوعد، ونسوا الحب،\nوخلوني وحدي بنار الأشواق.<br>\
                        يا ريتني ما حبيتهم،\nولا شفت منهم ذاك الفراق.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "عهد الوفاء", text: "عهد الوفاء، يبقى بگلبي،\nمهما طال الزمان، أو قصر.<br>\
                        أنا اللي أوفي، بكلمتي،\nحتى لو، كل الناس، تغيرت.<br>\
                        الحب الصادق، يبقى بگلبي،\nوغيرك أبد، ما حبيت ولا عشقت.<br>\
                        يا شمس عمري، يا ضوى سنيني،\nتظل بگلبي، حتى لو، أنت، اختفيت.", genres: ["love-romantic"] },
                    { title: "الحكمة في الصمت", text: "الحكمة في الصمت، مرات،\nأحسن من حكي، بلا معنى.\nالناس مقامات، مو كل شخص،\nيستاهل الوفا، والاهتمام.<br>\
                        عيش بسلام، ورفع راسك،\nترا الدنيا، ما بيها أي أمان.<br>\
                        واللي يخونك، اتركه،\nترا ما يستاهل، أي كلام.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "ليش الخيانة", text: "ليش الخيانة، صارت طبعكم،\nوليش الغدر، صار عنوانكم.<br>\
                        ما توقعت، منكم هذا،\nيا من كنت، أثق، بوعودكم.<br>\
                        القلب مجروح، والروح تبكي،\nعلى حب ضاع، بسبب غدركم.<br>\
                        يا ليتني، ما عرفتكم،\nولا شفت، منكم، هذا الهم.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "يا حبيبتي", text: "يا حبيبتي، يا أغلى من روحي،\nيا شمس عمري، يا أجمل قمر.<br>\
                        أحبك حباً، لا يوصفه كلام،\nيا كل أمنياتي، يا أغلى بشر.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبتي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "هموم الدنيا", text: "هموم الدنيا، تكسر الروح،\nوالقلب ينزف، من كثر الجروح.<br>\
                        الفقير يموت، من الجوع،\nوالغني، عايش، في أطيب الثياب.<br>\
                        وين العدالة؟ وين الحق؟\nصار الوطن، مثل بيت خراب.<br>\
                        يا رب، خلصنا من الظلم،\nوارزقنا، الفرج، يا وهاب.", genres: ["social-wisdom", "sad-melancholy"] },
                    { title: "نهاية العلاقة", text: "نهاية العلاقة، مؤلمة،\nإذا كانت مبنية، على الكذب.<br>\
                        الوفا مات، في قلوبكم،\nوالخيانة، صارت، أغلى هدف.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا التعب.<br>\
                        أعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها أي محب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "يا عراق الأصالة", text: "يا عراق الأصالة، يا مهبط الأنبياء،\nيا أرض الحضارات، يا أرض الكرامة.<br>\
                        بدمي أرويك، وبعيني أحميك،\nولأجلك، أقاتل، حتى القيامة.<br>\
                        الشعب العراقي، ما ينكسر،\nولرايته، يظل، مرفوع الهامة.<br>\
                        سنبني العراق، من جديد،\nونرفع رايته، في كل قمامة.", genres: ["bold-patriotic"] },
                    { title: "الأمل بالله", text: "الأمل بالله، ما يموت،\nحتى لو، كل الأبواب، انسدت.<br>\
                        هو القادر، على كل شيء،\nوهو اللي، يفتح، كل العقدة.<br>\
                        لا تيأس، من رحمة ربك،\nفالله، موجود، وهو السندة.<br>\
                        عيش بقوة، وبروح صلبة،\nترا كل صعب، يجي بعده سهلة.", genres: ["social-wisdom"] },
                    { title: "حنين الروح", text: "حنين الروح، إليك يا حبيبي،\nوالقلب ينزف، من كثر الشوق.<br>\
                        متى تجي، وتداوي جروحي،\nيا شمس عمري، يا أحلى ورد.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic", "sad-melancholy"] }
                ]
            },
            "basem-alabadi": {
                name: "باسم العبادي",
                poems: [
                    { title: "طيفك", text: "طيفك، ما يفارگ عيني،\nوكل لحظة تمر، تذكرني بيك.<br>\
                        يا ليتني، يمك، أضمك،\nوأنسى كلشي، وأنسى السنين.<br>\
                        الروح ذبلت، من كثر البچي،\nوالقلب مجروح، ما يرضى يلين.<br>\
                        يا دنيا، كافي عذاب،\nترا روحي، ملت، من هذا الحنين.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "أيام الفراق", text: "أيام الفراق، مؤلمة،\nتكسر القلب، وتخلي الروح، تبكي.<br>\
                        الخيانة طعنت، في ظهري،\nوخلتني، عايش، في هموم، وشكي.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا التعب.<br>\
                        أعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي مكسب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "حكمة الزمن", text: "حكمة الزمن، تگول،\nلا تثق، بوعود، كاذبة.<br>\
                        تراها تتغير، مع كل ظروف،\nواللي يبيعك، باعه، ما بيها، أي حجة.<br>\
                        عيش بصدقك، وبوفاك،\nترا هو اللي ينفعك، ويبقى لك، يا حجة.<br>\
                        واللي يخونك، اتركه،\nترا ما يستاهل، أي رجعة.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "يا أغلى حب", text: "يا أغلى حب، في هذا الوجود،\nيا شمس عمري، يا أجمل وعود.<br>\
                        حبك بگلبي، يروي سنيني،\nوغيرك أبد، ما أحب ولا أرتعد.<br>\
                        أنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى سند.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.", genres: ["love-romantic"] },
                    { title: "ليش الغدر", text: "ليش الغدر، صار طبعكم،\nوليش الخيانة، صارت أفعالكم.<br>\
                        ما توقعت، منكم هذا،\nيا من كنت، أثق، بوعودكم.<br>\
                        القلب مجروح، والروح تبكي،\nعلى حب ضاع، بسبب غدركم.<br>\
                        يا ليتني، ما عرفتكم،\nولا شفت، منكم، هذا الهم.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "صبر ايوب", text: "صبر ايوب، أخذته مني،\nعلى هموم الدنيا، اللي ما تخلص.<br>\
                        الروح تعبت، والجسد انهار،\nوالفرح غاب، وما رجع أبد.<br>\
                        يا رب، خلصني من هذا العذاب،\nوارزقني، السلام، والراحة.<br>\
                        ترا روحي، ملت،\nمن هذا القهر، وهذا الوهن.", genres: ["sad-melancholy", "social-wisdom"] },
                    { title: "يا وطني يا نبضي", text: "يا وطني يا نبضي، يا كل دنيتي،\nيا تراب الأجداد، يا أغلى ما عندي.<br>\
                        بدمي أرويك، وبعيني أحميك،\nولأجلك، أفدي روحي، وبكل جهدي.<br>\
                        الشعب العراقي، ما ينكسر،\nولرايته، يظل، مرفوع الهامة.<br>\
                        سنبني العراق، من جديد،\nونرفع رايته، في كل قمامة.", genres: ["bold-patriotic"] },
                    { title: "كلمات حكيمة", text: "كلمات حكيمة، من القلب،\nلا تبيع، ضميرك، بأي ثمن.<br>\
                        فالضمير، هو اللي يبقى،\nوالوفا، هو اللي ينفع، في كل زمن.<br>\
                        عيش بصدقك، وبوفاك،\nترا الكذب، حبله، دوم قصير.<br>\
                        واللي يغدر، ما يربح،\nوعاقبته، تكون، هي المصير.", genres: ["social-wisdom"] },
                    { title: "حنين العاشق", text: "حنين العاشق، يقتل الروح،\nإذا كان الشوق، ما عنده حدود.<br>\
                        على ولف راح، وما يدري بحالي،\nوالقلب مجروح، ما يطيب يعود.<br>\
                        يا ليتني، يمك، أضمك،\nوأنسى كلشي، وأنسى الوجود.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل الوعود.", genres: ["love-romantic", "sad-melancholy"] },
                    { title: "درس الخيانة", text: "درس الخيانة، مؤلم،\nيعلمك قيمة اللي يوفون.<br>\
                        لا تثق بالناس كلها،\nفبعضهم، يغدرون ويخونون.<br>\
                        حافظ على نفسك، من الشرور،\nوعيش بضميرك، مهما يكونون.<br>\
                        ترا اللي يحبك، يظل وياك،\nواللي يبيعك، ما يستاهلون.", genres: ["betrayal-separation", "social-wisdom"] }
                ]
            },
            "yasser-fleyh": {
                name: "ياسر فليح",
                poems: [
                    { title: "يا ولفي", text: "يا ولفي، يا گلبي، يا عيني،\nيا شمس عمري، يا أجمل حبيب.\nأنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل النصيب.\nيا شمس الدنيا، يا ضوى سنيني،\nتظل بگلبي، وما تروح، يا طبيب.", genres: ["love-romantic"] },
                    { title: "وجع الفراق", text: "وجع الفراق، يكسر الروح،\nويخلي القلب، يعيش في عذاب.<br>\
                        من يوم اللي رحت، ما شفت راحة،\nوالدمع يجري، على الخدود، مثل السحاب.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا العتاب.<br>\
                        صرت عايش، على الذكريات،\nوالروح تصرخ، من كثر الغياب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "نصيحة ذهبية", text: "نصيحة ذهبية، من القلب،\nلا تركض ورا الكذب، تتعب.<br>\
                        عيش بصدقك، وبوفاك،\nترا هو اللي ينفعك، وما بيه عجب.<br>\
                        الصديق الصادق، كنز،\nوالخاين، ما عنده، أي كذب.<br>\
                        عيش بسلام، ورفع راسك،\nترا الله وياك، وهو، اللي يكتب.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "أحبك يا نبض", text: "أحبك يا نبض، گلبي،\nيا روحي، يا كل أمنياتي.<br>\
                        أنت النور، الذي يضيء دربي،\nوأنت الأمل، في كل حياتي.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل الذكريات.", genres: ["love-romantic"] },
                    { title: "دموع العين", text: "دموع العين، تجري مثل النهر،\nعلى ولف راح، وما يدري بالقهر.<br>\
                        يا ليتني، ما عرفته،\nولا شفت منه، ذاك الغدر.<br>\
                        الوفا خاين، والحب كذاب،\nوالدنيا كلها، تزيدني تعسر.<br>\
                        يا رب أرحم بحالي،\nخلصني من هذا، كافي قهر.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "حكم القدر", text: "حكم القدر، ما يتغير،\nواللي مكتوب، لازم يصير.<br>\
                        لا تعاتب، نفسك، على شي،\nترا كل شي، بأمر الله، يسير.<br>\
                        عيش بقوة، وبروح صلبة،\nترا الحياة، اختبار، كبير.<br>\
                        واللي يصبر، ينال الفرج،\nوالله وياك، وهو خير المجير.", genres: ["social-wisdom"] },
                    { title: "وطن الجروح", text: "وطن الجروح يا عراق،\nشگد بكت عيوني لأجلك.\nكل شبر منك يحكي قصة،\nوبكل دمعة، أكتبلك أحبك.\nيا تاريخ مجدنا،\nمهما خانوا، سنبقى بجنبك.\nرايتك عالية، ما تنزل،\nيا تراب الوطن، فدوة لترابك.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "الغزل", text: "الغزل، فن، ما يعرفه كل واحد،\nبس اللي گلبه، محب، وحساس.<br>\
                        كلمات الحب، تطلع من الروح،\nوتلامس القلب، وتخليك، سعيد.<br>\
                        يا شمس عمري، يا ضوى سنيني،\nأنا بلياك، ما أگدر أعيش.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل الوجود.", genres: ["love-romantic"] },
                    { title: "وداع مؤلم", text: "وداع مؤلم، ما أنساه،\nخلاني أعيش، في عذاب.<br>\
                        الخيانة طعنت، في ظهري،\nوخلتني، وحدي، بين الصحاب.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت، منك، هذا العتاب.<br>\
                        أعيش وحدي، أحسنلي،\nترا الدنيا، ما بيها، أي أحباب.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "نور الأمل", text: "نور الأمل، يضيء دربي،\nحتى لو، كانت، الدنيا ظلام.<br>\
                        لا تيأس، من رحمة الله،\nفهو القادر، على كل مرام.<br>\
                        عيش بقوة، وبروح صلبة،\nترا الحياة، قصيرة، لا تنام.<br>\
                        واللي يؤمن بالله،\nما يخسر، ولا يندم، في كل الأيام.", genres: ["social-wisdom"] }
                ]
            },
            "adel-mohsen": {
                name: "عادل محسن",
                poems: [
                    { title: "دموع العين", text: "دموع العين، تجري مثل النهر،\nعلى ولف راح، وما يدري بالقهر.\nيا ليتني، ما عرفته،\nولا شفت منه، ذاك الغدر.\nالوفا خاين، والحب كذاب،\nوالدنيا كلها، تزيدني تعسر.\nيا رب أرحم بحالي،\nخلصني من هذا، كافي قهر.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "يا شمس عمري", text: "يا شمس عمري، يا ضوى سنيني،\nيا أغلى من روحي، يا كل أمنياتي.\nأحبك حباً، لا يوصفه كلام،\nيا حبيبي، يا كل حياتي.\nعيوني تسهر، وتناطر جيتك،\nوروحي تفرح، لو شفتك يا غايتي.\nتظل بگلبي، طول العمر،\nيا حبيبي، يا كل سعادتي.", genres: ["love-romantic"] },
                    { title: "الحكمة في الحياة", text: "الحكمة في الحياة، تگول،\nلا تركض ورا السراب، تتعب.\nاختار طريقك، بعناية،\nترا الدنيا، كلها، مو بس لعب.<br>\
                        الصديق الصادق، كنز،\nوالخاين، ما عنده، أي كذب.<br>\
                        عيش بضميرك، ورفع راسك،\nترا الله، وياك، وهو، اللي يكتب.", genres: ["social-wisdom"] },
                    { title: "جرح الغدر", text: "جرح الغدر، ما يلتئم بسهولة،\nتترك آثار، في القلب، ما تروح.<br>\
                        من اللي كنت أثق بيهم،\nجاني الطعن، وخلاني، في الجروح.<br>\
                        يا ليتني، ما عرفت الدنيا،\nولا شفت منها، هذا الوجوه.<br>\
                        لكن أبد، ما أنسى،\nاللي خانني، واللي تركني وحدي.", genres: ["betrayal-separation", "sad-melancholy"] },
                    { title: "يا روح الروح", text: "يا روح الروح، يا كل عمري،\nيا شمس الدنيا، يا أجمل قمر.\nحبك بگلبي، يروي سنيني،\nوغيرك أبد، ما أحب ولا أرتعد.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، مثل الوردة اللي بتبكي.<br>\
                        تظل بگلبي، طول العمر،\nيا حبيبي، يا كل النظر.", genres: ["love-romantic"] },
                    { title: "الأمل في الله", text: "الأمل في الله، ما يموت،\nحتى لو، كل الأبواب، انسدت.<br>\
                        هو القادر، على كل شيء،\nوهو اللي، يفتح، كل العقدة.<br>\
                        لا تيأس، من رحمة ربك،\nفالله، موجود، وهو السندة.<br>\
                        عيش بقوة، وبروح صلبة،\nترا كل صعب، يجي بعده سهلة.", genres: ["social-wisdom"] },
                    { title: "وداع الأحباء", text: "وداع الأحباء، يكسر الروح،\nويخلي القلب، يعيش في ظلام.<br>\
                        من اللي كنت أحبه، راح،\nوتركني وحدي، في هذا الأوهام.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت، منه، هذا الهيام.<br>\
                        لكن أبد، ما أنسى،\nاللي غدرني، في هذا العذاب.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "وطن صابر", text: "وطن صابر، رغم الجروح،\nيرفع راسه، في وجه العواصف.<br>\
                        الشعب صامد، لا ينحني،\nويقاتل، لأجل، الحق، والعواصف.<br>\
                        يا عراق، يا أغلى وطن،\nسنبقى نحميك، من كل الظروف.<br>\
                        رايتك عالية، ما تنزل،\nيا حبيبي، يا كل الحدود.", genres: ["bold-patriotic", "sad-melancholy"] },
                    { title: "نار الحب", text: "نار الحب، تحرگ بگلبي،\nوالروح تصرخ، من كثر الحنين.<br>\
                        يا ليتني، يمك، أضمك،\nوأنسى كلشي، وأنسى السنين.<br>\
                        أنت الروح، وأنت النبض،\nوأنت اللي في عيني، أغلى زين.<br>\
                        أنا بلياك، ما أگدر أعيش،\nروحي تذبل، يا أجمل عين.", genres: ["love-romantic"] },
                    { title: "الحكمة في الصبر", text: "الحكمة في الصبر، كنوز،\nتفتح لك، كل الأبواب.<br>\
                        لا تتعجل، على رزقك،\nترا الله، يعطيك، من غير حساب.<br>\
                        عيش بسلام، ورفع راسك،\nترا الدنيا، ما بيها أي عذاب.<br>\
                        واللي يصبر، ينال الفرج،\nوالله وياك، وهو خير الأحباب.", genres: ["social-wisdom"] }
                ]
            },
            "dhia-almiayali": {
                name: "ضياء الميالي",
                poems: [
                    { title: "يا دموع العين", text: "يا دموع العين، كافي بچي،\nترا القلب، تعب، من كثر الألم.<br>\
                        الوفا راح، والصدق غاب،\nوالخيانة طبع، بأهل الندم.<br>\
                        يا ليتني، ما عرفت الحب،\nولا شفت منك، هذا الظلم.<br>\
                        صرت عايش، على الذكريات،\nوالروح تصرخ، من كثر الندم.", genres: ["sad-melancholy", "betrayal-separation"] },
                    { title: "حبك قدر", text: "حبك قدر، ما أگدر أغيره،\nيا نبض گلبي، يا أجمل حلم.<br>\
                        من يوم اللي شفتك، عيني ما نامت،\nوغيرك أبد، ما عرفت طعم.<br>\
                        يا شمس عمري، يا ضوى سنيني،\nأنا بلياك، مثل وردة بلا دم.<br>\
                        تبقى بگلبي، طول العمر،\nيا حبيبي، يا أغلى اسم.", genres: ["love-romantic"] },
                    { title: "نصيحة للحياة", text: "نصيحة للحياة، عيش بضمير،\nترا الدنيا، ما بيها أمان.\nالناس أصناف، بيها الخير والشر،\nواللي يغدر، ما عنده، أي مكان.<br>\
                        عيش بصدقك، وبوفاك،\nترا هو اللي ينفعك، طول الزمان.<br>\
                        واللي يخونك، اتركه،\nترا ما يستاهل، أي إنسان.", genres: ["social-wisdom", "betrayal-separation"] },
                    { title: "غدر الزمن", text: "غدر الزمن، يكسر الروح،\nويخلي القلب، يعيش في ظلام.<br>\
                        من اللي كنت أثق بيهم،\nجاني الطعن،

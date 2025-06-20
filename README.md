<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Tajawal for Arabic support -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <!-- Font Awesome for social media icons and search -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" xintegrity="sha512-R4R/Y8A+Kz/q3F+G9+Y8zF1+W+g7/Q/n6Gz+g/Y7+W8/W9+N7/X6+T7/G6+Z9+F8/V7/T6/F5/R4/V3/T2/G1/Z0/A9/B8/C7/D6/E5/F4/I3/J2/K1/L0/M9/N8/O7/P6/Q5/R4/S3/T2/U1/V0/W9/X8/Y7/Z6/a5/b4/c3/d2/e1/f0/g9/h8/i7/j6/k5/l4/m3/n2/o1/p0/q9/r8/s7/t6/u5/v4/w3/x2/y1/z0/A9/B8/C7/D6/E5/F4/G3/H2/I1/J0/K9/L8/M7/N6/O5/P4/Q3/R2/S1/T0/U9/V8/W7/X6/Y5/Z4/a3/b2/c1/d0/e9/f8/g7/h6/i5/j4/k3/l2/m1/n0/o9/p8/q7/r6/s5/t4/u3/v2/w3/x2/y1/z0" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        /* Global Styles */
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #FAF9F6; /* Light beige/off-white background */
            color: #333; /* Soft dark grey for general text */
            line-height: 1.8; /* Increased line height for readability of poetry */
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

        /* Smooth slide-in animation for poetry sections */
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
            white-space: nowrap; /* Prevent wrapping for long category names */
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

        /* Adjustments for Hero Section padding */
        #hero {
            padding-top: 10rem; /* Adjusted for smaller screens / to move content down */
            min-height: 100vh; /* Ensure it takes full viewport height */
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* General poem card styling */
        .poem-card {
            background-color: white;
            border-radius: 0.75rem; /* rounded-lg */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* shadow-md */
            overflow: hidden;
            padding: 1.5rem; /* p-6 */
            margin-bottom: 2rem; /* space between cards */
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
                font-size: 0.9rem; /* Smaller nav links on mobile */
                margin: 0 0.25rem; /* Less space between nav items */
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
            .poem-card .p-6 { /* Note: poem-card itself has padding now */
                padding: 1rem; /* Adjust if needed */
            }
            .poem-card h3 {
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
            .poem-card h3 {
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
                    <!-- Logo Placeholder (Right aligned for RTL) -->
                    <div>
                        <a href="#" class="text-3xl font-bold text-gray-800 hover:text-orange-500 transition duration-300">
                            موسوعة الشعر العراقي
                        </a>
                    </div>
                    <!-- Navigation Bar - Categories and direct links -->
                    <ul class="flex flex-wrap justify-center space-x-4 space-x-reverse md:space-x-6 md:space-x-reverse mt-4 md:mt-0">
                        <li><a href="#hero" class="nav-link text-lg font-medium">الرئيسية</a></li>
                        <li><a href="#poets-section" class="nav-link text-lg font-medium">الشعراء</a></li>
                        <li><a href="#love-poems" class="nav-link text-lg font-medium">شعر الحب والغزل</a></li>
                        <li><a href="#romantic-poems" class="nav-link text-lg font-medium">شعر الرومانسية</a></li>
                        <li><a href="#bold-poems" class="nav-link text-lg font-medium">شعر الجرأة</a></li>
                        <li><a href="#other-genres" class="nav-link text-lg font-medium">أنواع أخرى</a></li>
                        <li><a href="#newsletter-subscription" class="nav-link text-lg font-medium">تواصل معنا</a></li>
                    </ul>
                </div>
                <!-- Search Bar - Large and Below Navigation Links -->
                <div class="relative w-full mt-4">
                    <input type="text" placeholder="ابحث عن قصائد، شعراء، أو كلمات..." class="search-input w-full p-3 md:p-4 text-lg border border-gray-300 rounded-full focus:ring-0 text-right pr-12">
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
                مرحباً بك في <span class="text-orange-500">موسوعة الشعر العراقي</span>
            </h1>
            <p class="text-2xl md:text-3xl text-gray-600 mb-10 animate-fade-in animation-delay-200">
                بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين
            </p>
            <a href="#featured-poems" class="btn-primary bg-orange-500 text-white text-xl md:text-2xl font-semibold py-4 px-10 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 animate-fade-in animation-delay-400">
                ابدأ التصفح
            </a>
        </div>
    </section>

    <!-- Poets Section - New structure to list poets -->
    <section id="poets-section" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعراء عراقيون مبدعون</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
            <!-- Poet Card: سمير صبيح -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl">
                <img src="https://placehold.co/200x200/8B5E3C/FAF9F6?text=Samir+Subaih" alt="صورة الشاعر سمير صبيح" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">سمير صبيح</h3>
                <p class="text-gray-600 text-sm">أحد أبرز شعراء العراق، معروف بقصائده العميقة والمليئة بالمشاعر الإنسانية.</p>
                <a href="#samir-subaih-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: جبار رشيد -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-100">
                <img src="https://placehold.co/200x200/EEDC82/8B5E3C?text=Jabbar+Rasheed" alt="صورة الشاعر جبار رشيد" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">جبار رشيد</h3>
                <p class="text-gray-600 text-sm">شاعر متميز بقصائده الرومانسية والغزلية التي تأسر القلوب.</p>
                <a href="#jabbar-rasheed-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: علي رشم -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-200">
                <img src="https://placehold.co/200x200/FFA500/FAF9F6?text=Ali+Rasham" alt="صورة الشاعر علي رشم" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">علي رشم</h3>
                <p class="text-gray-600 text-sm">يمتلك أسلوباً جريئاً ومعبراً، يتناول قضايا المجتمع بصدق.</p>
                <a href="#ali-rasham-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: كاظم إسماعيل الكاطع -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-300">
                <img src="https://placehold.co/200x200/F4F1EE/8B5E3C?text=Kadhim+Al-Katiah" alt="صورة الشاعر كاظم إسماعيل الكاطع" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">كاظم إسماعيل الكاطع</h3>
                <p class="text-gray-600 text-sm">من رواد الشعر الشعبي، اشتهر بقصائده العميقة والوطنية.</p>
                <a href="#kadhim-alkatiah-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: عريان السيد خلف -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-400">
                <img src="https://placehold.co/200x200/FAF9F6/8B5E3C?text=Aryan+Al-Sayyid+Khalaf" alt="صورة الشاعر عريان السيد خلف" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">عريان السيد خلف</h3>
                <p class="text-gray-600 text-sm">أيقونة الشعر الشعبي العراقي، بأسلوبه الفريد وقصائده المؤثرة.</p>
                <a href="#aryan-alsayyid-khalaf-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: محمد مهدي الجواهري -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-100">
                <img src="https://placehold.co/200x200/EEDC82/8B5E3C?text=Al-Jawahiri" alt="صورة الشاعر محمد مهدي الجواهري" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">محمد مهدي الجواهري</h3>
                <p class="text-gray-600 text-sm">نهر العراق الثالث، عملاق الشعر العربي، له مكانة فريدة.</p>
                <a href="#al-jawahiri-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائده</a>
            </div>
            <!-- Poet Card: نازك الملائكة -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden p-6 text-center poetry-card fade-in-slide-rtl animation-delay-200">
                <img src="https://placehold.co/200x200/FFA500/FAF9F6?text=Nazik+Al-Malaika" alt="صورة الشاعرة نازك الملائكة" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
                <h3 class="text-2xl font-semibold text-gray-800 mb-2">نازك الملائكة</h3>
                <p class="text-gray-600 text-sm">من رائدات الشعر الحر، أثرت الأدب العربي بأسلوبها المتجدد.</p>
                <a href="#nazik-almalaika-poems" class="text-orange-500 hover:underline mt-4 block">شاهد قصائدها</a>
            </div>
        </div>
    </section>

    <!-- Section: Love and Romance Poetry -->
    <section id="love-poems" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر الحب والغزل</h2>
        <div class="grid grid-cols-1 gap-8">
            <!-- Poem Card - Samir Subaih - Full Poem Example -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">يا روحي وكياني</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: سمير صبيح</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    يا روحي وكياني يا كل عمري <br>
                    يا دنيتي يالغايب عن عيني وساكن بفكري <br>
                    ما تغيب عني لو طال بي الدهر <br>
                    تبقى بقلبي ساكن يا حبي وعمري <br>
                    يا من سكنت الروح مني وعيني <br>
                    يا نجمة تضوي ليلي وسنيني <br>
                    يا أغلى من روحي يا نبض قلبي <br>
                    يا ريحة العنبر يا أغلى من الذهب
                </div>
            </div>

            <!-- Poem Card - Jabbar Rasheed - Full Poem Example -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">عطر المحبة</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: جبار رشيد</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    شميت عطرك وانسيت روحي <br>
                    يا دنيا ويا هلي يا نور عيني <br>
                    يا ريحة الورد يا عطر الياسمين <br>
                    يا حلم حياتي يا كل سنيني <br>
                    يا قصة حب ما تنتهي أبد <br>
                    يا أغلى من روحي ويا أغلى وعد <br>
                    يا ضحكة العين يا بسمة الشفاه <br>
                    يا نبض قلبي يا كل الحياة
                </div>
            </div>
        </div>
    </section>

    <!-- Section: Romantic Poetry -->
    <section id="romantic-poems" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر الرومانسية</h2>
        <div class="grid grid-cols-1 gap-8">
            <!-- Poem Card - Example of Romantic Poem -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">همسة في ليلٍ طويل</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: وهمي</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    في ليلٍ طويلٍ، سكونٌ يلفّ <br>
                    وهمسُ النسيمِ يروي شغف <br>
                    عيناكِ بحرٌ، فيهِ أغرقُ <br>
                    وقلبكِ مينائي، إليهِ أرتقي <br>
                    يا سحرَ الوجودِ، يا نبضَ الحياة <br>
                    بكِ تكتملُ الروحُ، وفيكِ المنى <br>
                    أنتِ القصيدةُ، أنتِ اللحنُ <br>
                    يا من ملكتِ القلبَ، وكنتِ السكن
                </div>
            </div>
            <!-- Another Romantic Poem -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">أنتِ قمري</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: وهمي</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    في ليالي العمرِ، أنتِ قمري <br>
                    تضيئين دربي، يا نجمةً تسري <br>
                    بابتسامتكِ، يشرقُ صباحي <br>
                    وبلمسةٍ منكِ، يزولُ جراحي <br>
                    يا وردةً فاحت، يا عطرَ الزمان <br>
                    في عيناكِ سرٌّ، وفي قلبكِ الأمان <br>
                    كلّما نظرتُ إليكِ، أرى الكون <br>
                    فأنتِ كلّي، وبكِ أكون
                </div>
            </div>
        </div>
    </section>

    <!-- Section: Bold Poetry -->
    <section id="bold-poems" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">شعر الجرأة</h2>
        <div class="grid grid-cols-1 gap-8">
            <!-- Poem Card - Ali Rasham - Full Poem Example -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">صوت الحق</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: علي رشم</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    لا تظن الصمت ضعفاً، فالسكوت أحياناً جواب <br>
                    والحق لا يموت، لو طال الزمن أو غاب <br>
                    صوتي يعلو، كالرعد في السحاب <br>
                    يفضح الظلم، ويكشف الأسباب <br>
                    لا أخشى الملامة، ولا أهاب العذاب <br>
                    كلماتي سيوفٌ، تقطع كل حجاب <br>
                    فالجرأة عقيدة، وليست مجرد خطاب <br>
                    وهذا هو دربي، وإن كثرت الذئاب
                </div>
            </div>
            <!-- Another Bold Poem -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">ثورة الأقلام</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: وهمي</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    يا من تظنون صمتنا جبناً <br>
                    أقلامنا تكتب تاريخاً ولحناً <br>
                    ثورةٌ في الأفكار، لا تعرف الوهنَ <br>
                    نقتحم الصعاب، ونبني وطناً <br>
                    لا قيود على فكرٍ، لا حصارَ على بيان <br>
                    صوتنا الحقّ، يدوّي في كلّ مكان <br>
                    فليعلم الظالمُ، أنّ النهايةَ قد حان <br>
                    فالحريةُ تنادي، وهذا هو الأوان
                </div>
            </div>
        </div>
    </section>

    <!-- Section: Other Genres - e.g., National, Social, Wisdom poetry -->
    <section id="other-genres" class="container mx-auto py-16 px-6 md:px-12">
        <h2 class="text-5xl font-bold text-gray-800 text-center mb-12">أنواع أخرى من الشعر</h2>
        <div class="grid grid-cols-1 gap-8">
            <!-- Example: National Poem - Abdul Karim Al-Qassab -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">يا دجلة الخير</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: عبد الكريم القصاب</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    يا دجلة الخير يا نبع الحياة <br>
                    يا أرض الأجداد يا كنز النجاة <br>
                    يا رمز العراقة يا فخر الوطن <br>
                    بكِ تشرق الشمس، وبكِ يزهر الزمن <br>
                    تاريخكِ مجدٌ، وحاضركِ عطاء <br>
                    يا أرض الرافدين، يا أرض السخاء <br>
                    فليحفظكِ الله، يا أرض السلام <br>
                    ويا عراقنا الغالي، يا أعلى مقام
                </div>
            </div>
            <!-- Example: Social Poem - Aryan Al-Sayyid Khalaf -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">الفقر</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: عريان السيد خلف</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    يا فقر يا سيف الجوع على رقاب الناس <br>
                    يا ليل الظلام يا هم الأنفاس <br>
                    كم من عيون باتت ساهرة <br>
                    تبكي على حالها، وتنتظر المعجزة <br>
                    يا قلوباً أرهقها العوز والمرض <br>
                    متى ينتهي الظلم، ويحل الفرج <br>
                    صرخة ألم، تعلو في كل مكان <br>
                    متى يشرق العدل، ويسود الأمان
                </div>
            </div>
            <!-- Example: Wisdom Poem - Kadhim Al-Katiah -->
            <div class="poem-card fade-in-slide-rtl">
                <h3 class="text-3xl font-semibold text-gray-800 mb-4">حكمة الأيام</h3>
                <p class="text-xl font-medium text-orange-600 mb-6">للشاعر: كاظم إسماعيل الكاطع</p>
                <div class="text-gray-700 text-lg leading-loose whitespace-pre-line">
                    الأيام دولاب، يدور على كل حال <br>
                    يوم لكَ ويوم عليك، هذا هو الحال <br>
                    لا تحزن على ما فات، فالعمر رحلة <br>
                    تعلم من الأخطاء، واصنع من الضعف قوة <br>
                    الحياة دروس، والزمن معلم <br>
                    كن قوياً، واجه الحياة بقلبٍ حكيم <br>
                    فالخير قادم، بعد كل عناء <br>
                    والصبر مفتاح، لكل رجاء
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter Subscription Section -->
    <section id="newsletter-subscription" class="bg-orange-100 py-16 px-6 md:px-12 text-center rounded-lg shadow-inner mx-auto max-w-4xl fade-in-slide-rtl" style="background-color: #EEDC82; margin-top: 4rem; margin-bottom: 4rem;">
        <h2 class="text-4xl font-bold text-gray-800 mb-6">اشترك لتصلك روائع الشعر</h2>
        <p class="text-xl text-gray-700 mb-8 max-w-2xl mx-auto">
            احصل على مختارات من أروع القصائد مباشرة في صندوق بريدك الوارد.
        </p>
        <div class="flex flex-col md:flex-row justify-center items-center gap-4">
            <input type="email" placeholder="أدخل بريدك الإلكتروني..." class="w-full md:w-1/2 p-4 rounded-full border-2 border-gray-300 focus:outline-none focus:border-orange-500 text-right text-lg">
            <button class="btn-primary bg-orange-500 text-white text-xl font-semibold py-4 px-8 rounded-full shadow-lg hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-orange-300 w-full md:w-auto" aria-label="اشترك الآن">
                اشترك الآن
            </button>
        </div>
    </section>

    <!-- Footer Section - Consolidated and Enhanced -->
    <footer id="about-us-footer" class="bg-gray-900 py-10 px-6 md:px-12 text-center text-gray-400">
        <div class="max-w-4xl mx-auto">
            <!-- Consolidated About Us & Copyright -->
            <h2 class="text-3xl font-bold text-gray-200 mb-4">موسوعة الشعر العراقي</h2>
            <p class="text-md text-gray-300 leading-relaxed mb-6">
                بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي، من عمالقة الشعر إلى الأصوات الشابة.
                نسعى لإثراء الساحة الأدبية وتقديم أرشيف متكامل يعكس جمال وعمق الكلمة العراقية.
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
                <!-- TikTok icon is not in Font Awesome 6.0.0-beta3 by default. Adding a custom SVG for it. -->
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-orange-400 transition duration-300 text-3xl" aria-label="TikTok">
                    <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12.016 0c-.815 0-.968.103-1.636.311-.667.208-1.229.544-1.64.954-.412.41-.749.973-.956 1.641C7.575 3.518 7.472 3.67 7.472 4.485v8.529c0 .815.103.968.311 1.636.208.667.544 1.229.954 1.64.41.412.973.749 1.641.956.668.208.82.311 1.635.311h.001c.815 0 .968-.103 1.636-.311.667-.208 1.229-.544 1.64-.954.412-.41.749-.973.956-1.641.208-.668.311-.82.311-1.635v-8.529c0-.815-.103-.968-.311-1.636-.208-.667-.544-1.229-.954-1.64a2.983 2.983 0 00-1.64-.956C12.983 0 12.831 0 12.016 0zm-1.042 3.498h2.083v8.529c0 .815-.103.968-.311 1.636-.208.667-.544 1.229-.954 1.64-.41.412-.973.749-1.641.956-.668.208-.82.311-1.635.311h-.001c-.815 0-.968-.103-1.636-.311-.667-.208-1.229-.544-1.64-.954-.412-.41-.749-.973-.956-1.641-.208-.668-.311-.82-.311-1.635V3.498zm6.541 0h2.083v8.529c0 .815-.103.968-.311 1.636-.208.667-.544 1.229-.954 1.64-.41.412-.973.749-1.641.956-.668.208-.82.311-1.635.311h-.001c-.815 0-.968-.103-1.636-.311-.667-.208-1.229-.544-1.64-.954-.412-.41-.749-.973-.956-1.641-.208-.668-.311-.82-.311-1.635V3.498z"/>
                    </svg>
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
        // JavaScript for Header Show/Hide on Scroll with "Frame" Positioning
        let lastScrollY = window.scrollY;
        const header = document.getElementById('main-header');
        const headerOffsetTrigger = 200; // Distance to scroll down before hiding header

        // Ensure header is visible on page load
        header.classList.add('header-visible');

        window.addEventListener('scroll', function() {
            if (window.scrollY > lastScrollY && window.scrollY > headerOffsetTrigger) {
                // Scrolling down and past the trigger point
                header.classList.remove('header-visible');
                header.classList.add('header-hidden');
            } else if (window.scrollY < lastScrollY || window.scrollY <= headerOffsetTrigger) {
                // Scrolling up or near the top
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

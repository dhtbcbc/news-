<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for icons (Hamburger, Search, Social Media, Copy) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Custom Colors and Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap'); /* Modern Arabic font */
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* Classic Arabic font for poem text */

        :root {
            --main-bg: #FFF2E0; /* Off-white background for the entire site */
            --dark-heading: #222222; /* Black for headings */
            --body-text: #444444; /* Dark gray for body text */
            --button-default-text: #000000; /* Black text on default buttons */
            --button-bg-default: #E0E0E0; /* Light gray for default button background */
            --button-hover-bg: #FFA500; /* Orange background on button hover/active */
            --button-hover-text: white; /* White text on orange buttons */
            --footer-bg: #222831; /* Dark blue/black for footer, as per request */
            --footer-text: #EEEEEE; /* Light text for footer */
            --footer-link-hover: #FFA500; /* Orange hover for footer links */
            --poet-card-border: #8B5E3C; /* Warm brown for poet card border */
            --copy-button-bg: #00ADB5; /* Turquoise for copy button */
            --copy-button-hover-bg: #008C99; /* Darker turquoise on hover */
            --hamburger-bg: rgba(255, 255, 255, 0.7); /* Slightly translucent white for hamburger background */
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--main-bg); /* Apply main background to entire body */
            color: var(--body-text);
            line-height: 1.8;
            scroll-behavior: smooth;
            overflow-x: hidden; /* Prevent horizontal scroll */
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--main-bg);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb {
            background: var(--accent-orange);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-brown);
        }

        /* --- Header Specific Styles --- */
        .fixed-header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 50;
            background-color: var(--main-bg); /* Same as main background for seamless look */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05); /* Soft shadow */
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            padding: 1rem 1.5rem; /* Adjusted padding */
            display: flex;
            align-items: center;
            justify-content: space-between; /* Distribute items */
        }

        .header-hidden {
            transform: translateY(-100%);
        }

        /* Website Title in Header */
        .header-title {
            font-size: 2.2rem; /* Adjusted for tighter fit */
            font-weight: 800; /* Extra bold */
            color: var(--dark-heading);
            white-space: nowrap; /* Prevent wrapping */
            flex-shrink: 0; /* Don't shrink */
            margin-left: 1rem; /* Space from search bar */
        }

        /* Search Bar within Header */
        .header-search-container {
            flex-grow: 1; /* Allow search bar to take available space */
            position: relative;
        }
        .header-search-input {
            width: 100%;
            padding: 0.75rem 1rem 0.75rem 2.5rem; /* Padding for text and icon */
            border-radius: 9999px;
            border: 2px solid var(--accent-orange);
            background-color: white; /* White background for search input */
            color: var(--dark-heading);
            font-size: 1rem;
            box-shadow: inset 0 1px 3px rgba(0,0,0,0.05);
            transition: border-color 0.2s ease, box-shadow 0.2s ease;
        }
        .header-search-input::placeholder {
            color: var(--body-text);
            opacity: 0.7;
        }
        .header-search-input:focus {
            outline: none;
            border-color: var(--accent-brown);
            box-shadow: 0 0 0 3px rgba(139, 94, 60, 0.2); /* Focus ring for brown */
        }
        .header-search-icon {
            position: absolute;
            left: 1rem; /* Position from left in RTL */
            top: 50%;
            transform: translateY(-50%);
            color: var(--body-text);
            font-size: 1.1rem;
        }

        /* Hamburger Menu Toggle */
        .hamburger-toggle {
            color: var(--dark-heading);
            font-size: 2.2rem;
            cursor: pointer;
            padding: 0.5rem;
            transition: color 0.2s ease, background-color 0.2s ease, border-radius 0.2s ease;
            flex-shrink: 0; /* Don't shrink */
            margin-right: 0.5rem; /* Space from search bar */
            background-color: var(--hamburger-bg); /* Explicit background */
            border-radius: 8px; /* Slightly rounded */
        }
        .hamburger-toggle:hover {
            color: var(--accent-orange);
            background-color: rgba(255, 165, 0, 0.1); /* Subtle hover for background */
        }

        /* --- Hero Section Styles --- */
        .hero-section {
            padding: 5rem 1rem;
            text-align: center;
        }
        .hero-title {
            font-size: 3.5rem;
            font-weight: 800;
            color: var(--dark-heading);
            line-height: 1.3;
        }
        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--body-text);
            max-width: 800px;
            margin: 1.5rem auto 0;
            line-height: 1.6;
        }

        /* --- Poet Grid Card --- */
        .poet-grid-card {
            background-color: white;
            border-radius: 12px;
            padding: 24px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border-top: 5px solid var(--poet-card-border);
            position: relative;
            overflow: hidden;
            display: flex; /* For vertical centering of text */
            align-items: center;
            justify-content: center;
            min-height: 150px; /* Ensure consistent height */
        }
        .poet-grid-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
            background-color: #FFFBF5; /* Slight hover background */
        }
        .poet-grid-card h3 {
            color: var(--dark-heading);
            font-size: 2rem;
            font-weight: 700;
            margin: 0; /* Remove default margin */
            transition: color 0.2s ease;
        }
        .poet-grid-card:hover h3 {
            color: var(--accent-orange); /* Text color change on hover */
        }

        /* --- Poet Detail Page (New Section, not Modal) --- */
        #poet-detail-page {
            background-color: var(--main-bg); /* Same as main background */
            padding: 2.5rem 1.5rem; /* Consistent padding */
            border-radius: 15px; /* Rounded corners for the "page" itself */
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1); /* Subtle shadow */
            margin-top: 2rem; /* Space from header */
            position: relative; /* For the "Back to Poets" button */
            min-height: 80vh; /* Ensure it looks like a full page */
        }

        #poet-detail-page .back-to-poets-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background-color: var(--button-bg-default);
            color: var(--button-default-text);
            padding: 0.75rem 1.5rem;
            border-radius: 9999px;
            font-weight: 700;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        #poet-detail-page .back-to-poets-btn:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-text);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        /* Poet Detail Content */
        #poet-detail-name-display {
            font-size: 3rem;
            font-weight: 800;
            color: var(--dark-heading);
            margin-bottom: 1.5rem;
            text-align: center;
            border-bottom: 2px solid var(--accent-orange); /* Underline for name */
            padding-bottom: 10px;
        }
        #poet-detail-bio-display {
            font-size: 1.1rem;
            color: var(--body-text);
            line-height: 2;
            margin-bottom: 2.5rem;
            padding: 0 1rem;
            text-align: justify;
        }

        /* Category Buttons within Poet Detail Page */
        .category-pill {
            background-color: var(--button-bg-default); /* Default light gray */
            color: var(--button-default-text); /* Black text */
            padding: 0.75rem 1.5rem;
            border-radius: 9999px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .category-pill:hover, .category-pill.active {
            background-color: var(--button-hover-bg); /* Orange on hover/active */
            color: var(--button-hover-text); /* White text */
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        /* Individual Poem Display (Full Text Directly) within Poet Detail Page */
        .poem-full-card {
            background-color: white; /* White background for poem cards */
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            margin-bottom: 1.5rem;
            border-right: 4px solid var(--accent-orange); /* Artistic border */
            position: relative; /* For copy button positioning */
        }
        .poem-full-card h4 {
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--dark-heading);
            margin-bottom: 1rem;
            border-bottom: 1px solid rgba(0,0,0,0.1);
            padding-bottom: 0.75rem;
            text-align: center;
        }
        .poem-full-card .poem-text {
            font-family: 'Amiri', serif; /* Classic font for poem text */
            font-size: 1.1rem;
            white-space: pre-line; /* Preserves line breaks */
            line-height: 2.2; /* Generous line height for poetry */
            color: var(--body-text);
            text-align: justify;
            padding-bottom: 1.5rem; /* Space for copy button */
        }

        .copy-button {
            position: absolute;
            bottom: 10px;
            left: 10px;
            background-color: var(--copy-button-bg);
            color: white;
            padding: 0.5rem 0.8rem;
            border-radius: 8px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: background-color 0.2s ease, transform 0.2s ease;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .copy-button:hover {
            background-color: var(--copy-button-hover-bg);
            transform: translateY(-1px);
        }
        .copy-button i {
            font-size: 1rem;
        }

        /* --- Mobile Sidebar Menu --- */
        #mobile-sidebar {
            position: fixed;
            top: 0;
            right: -250px; /* Hidden initially */
            width: 250px;
            height: 100%;
            background-color: var(--accent-brown); /* Darker for contrast */
            box-shadow: -5px 0 15px rgba(0,0,0,0.3);
            transition: right 0.3s ease-in-out;
            z-index: 90;
            padding-top: 60px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        #mobile-sidebar.open {
            right: 0;
        }
        #mobile-sidebar a {
            display: block;
            padding: 15px 20px;
            color: white;
            font-size: 1.2rem;
            text-decoration: none;
            transition: background-color 0.2s ease;
            width: 100%;
            text-align: center;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        #mobile-sidebar a:last-child {
            border-bottom: none;
        }
        #mobile-sidebar a:hover {
            background-color: rgba(255,255,255,0.1);
        }
        #mobile-sidebar .close-btn {
            position: absolute;
            top: 10px;
            left: 20px;
            font-size: 2.5rem;
            color: white;
            cursor: pointer;
        }

        /* --- Footer Styles --- */
        .site-footer {
            background-color: var(--footer-bg); /* Dark background */
            color: var(--footer-text); /* Light text */
            padding: 3rem 1.5rem;
            text-align: center;
            margin-top: 4rem; /* Space from main content */
        }
        .site-footer .footer-title {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
        }
        .site-footer .footer-description {
            font-size: 1rem;
            line-height: 1.6;
            max-width: 700px;
            margin: 0 auto 1.5rem;
        }
        .site-footer .copyright-text {
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }
        .site-footer .footer-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.5rem;
            font-size: 1rem;
            margin-bottom: 2rem;
        }
        .site-footer .footer-links a {
            color: var(--footer-text);
            text-decoration: none;
            transition: color 0.2s ease;
        }
        .site-footer .footer-links a:hover {
            color: var(--footer-link-hover);
            text-decoration: underline;
        }
        .site-footer .social-icons {
            display: flex;
            justify-content: center;
            gap: 2rem;
        }
        .site-footer .social-icons a {
            color: var(--footer-text);
            font-size: 2.5rem; /* Larger icons */
            transition: color 0.2s ease, transform 0.2s ease;
            text-decoration: none; /* Remove underline from icons */
            display: flex; /* To center icon if text is added later */
            align-items: center;
            gap: 0.5rem;
        }
        .site-footer .social-icons a:hover {
            color: var(--footer-link-hover);
            transform: translateY(-3px); /* Slight lift on hover */
        }

        /* --- Responsive Adjustments --- */
        @media (max-width: 768px) {
            .fixed-header {
                flex-wrap: wrap;
                padding: 0.8rem 1rem;
            }
            .header-title {
                width: 100%; /* Take full width on small screens */
                text-align: center;
                margin-bottom: 0.5rem;
                font-size: 1.8rem;
                order: -1; /* Place title first */
            }
            .header-search-container {
                width: calc(100% - 60px); /* Adjust width to make space for hamburger */
                margin: 0.5rem 0; /* Add vertical margin */
            }
            .hamburger-toggle {
                position: absolute; /* Position relative to header */
                left: 1rem;
                top: 0.8rem;
            }

            .hero-section { padding: 3rem 1rem; }
            .hero-title { font-size: 2.5rem; }
            .hero-subtitle { font-size: 1.2rem; }

            .poet-grid-card h3 { font-size: 1.6rem; }

            #poet-detail-page { padding: 1.5rem 1rem; margin-top: 1rem; }
            #poet-detail-page .back-to-poets-btn {
                top: 15px;
                right: 15px;
                padding: 0.6rem 1rem;
                font-size: 0.85rem;
            }
            #poet-detail-name-display { font-size: 2rem; margin-bottom: 1rem; }
            #poet-detail-bio-display { font-size: 0.95rem; line-height: 1.8; margin-bottom: 1.5rem; padding: 0;}
            .category-pill { padding: 0.5rem 1rem; font-size: 0.85rem; }
            .poem-full-card h4 { font-size: 1.4rem; }
            .poem-full-card .poem-text { font-size: 1rem; line-height: 1.8;}

            .copy-button {
                padding: 0.4rem 0.7rem;
                font-size: 0.8rem;
            }
            .copy-button i {
                font-size: 0.9rem;
            }

            .site-footer {
                padding: 2rem 1rem;
            }
            .site-footer .footer-title {
                font-size: 2rem;
            }
            .site-footer .footer-description {
                font-size: 0.9rem;
            }
            .site-footer .copyright-text {
                font-size: 0.8rem;
            }
            .site-footer .footer-links {
                flex-direction: column;
                gap: 0.5rem;
                margin-bottom: 1rem;
            }
            .site-footer .social-icons {
                flex-direction: row; /* Keep social icons horizontal */
                gap: 1.5rem;
            }
            .site-footer .social-icons a {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Top Header (Fixed Navigation Bar) -->
    <header id="main-header" class="fixed-header">
        <!-- Website Title -->
        <h1 class="header-title">موسوعة الشعر العراقي</h1>

        <!-- Search Bar -->
        <div class="header-search-container relative">
            <input type="text" id="search-input" placeholder="ابحث عن شاعر أو قصيدة..." class="header-search-input">
            <i class="fas fa-search header-search-icon"></i>
        </div>

        <!-- Hamburger Menu Toggle -->
        <button id="hamburger-menu-toggle" class="hamburger-toggle">
            <i class="fas fa-bars"></i>
        </button>
    </header>

    <!-- Mobile Sidebar Menu (Serves as the main navigation for all screens) -->
    <div id="mobile-sidebar">
        <button class="close-btn" onclick="closeMobileMenu()">&times;</button>
        <a href="#" data-section="home" onclick="showSection('home')">الصفحة الرئيسية</a>
        <a href="#" data-section="poets" onclick="showSection('poets')">الشعراء</a>
        <a href="#" data-section="love" onclick="showSection('love')">الحب</a>
        <a href="#" data-section="separation" onclick="showSection('separation')">الفراق</a>
        <a href="#" data-section="longing" onclick="showSection('longing')">الحنين</a>
        <a href="#" data-section="ghazal" onclick="showSection('ghazal')">الغزل</a>
        <a href="#" data-section="wisdom" onclick="showSection('wisdom')">الحكمة</a>
        <!-- Add more categories here as needed -->
    </div>

    <!-- Main Content Area -->
    <main class="container mx-auto px-4">
        <!-- Offset for fixed header -->
        <div class="h-[100px] sm:h-[100px] md:h-[80px]"></div>

        <!-- Hero Section - Layer 1 -->
        <section id="home-section" class="content-section active hero-section">
            <h2 class="hero-title hero-text">مرحبًا بك في موسوعة الشعر العراقي</h2>
            <p class="hero-subtitle hero-text">بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين</p>
        </section>

        <!-- Poets Section (Grid of Names) - Layer 1 -->
        <section id="poets-section" class="content-section py-10 sm:py-16">
            <h2 class="text-4xl font-bold text-dark-heading text-center mb-10">الشعراء</h2>
            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <!-- Poet cards will be dynamically generated here by JS -->
            </div>
        </section>

        <!-- Poet Detail Page - Layer 2 (Full page, not a modal) -->
        <section id="poet-detail-page" class="content-section py-10 sm:py-16 hidden">
            <!-- Back to Poets List Button -->
            <button class="back-to-poets-btn" onclick="showSection('poets')">
                العودة إلى الشعراء
            </button>

            <!-- Poet Info -->
            <h2 id="poet-detail-name-display" class="mt-10"></h2>
            <p id="poet-detail-bio-display"></p>

            <!-- Poem Categories -->
            <h3 class="text-3xl font-bold text-dark-heading text-center mb-6 mt-8">قصائد الشاعر</h3>
            <div id="poem-categories" class="flex flex-wrap justify-center gap-3 mb-8">
                <!-- Category buttons will be generated here -->
            </div>
            <div id="poems-display">
                <!-- Poems with title and full text will load directly here -->
            </div>
        </section>
    </main>

    <!-- Footer - Separate Visual Block -->
    <footer class="site-footer">
        <div class="container mx-auto">
            <h4 class="footer-title">موسوعة الشعر العراقي</h4>
            <p class="footer-description">
                بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي، من عمالقة الشعر إلى الأصوات الشابة. نسعى لإثراء الساحة الأدبية وتقديم أرشيف متكامل يعكس جمال وعمق الكلمة العراقية.
            </p>
            <p class="copyright-text">
                &copy; <span id="current-year-footer"></span> كرار حيدر. جميع الحقوق محفوظة.
            </p>
            <div class="footer-links">
                <a href="#">سياسة الخصوصية</a>
                <span>|</span>
                <a href="#">شروط الاستخدام</a>
            </div>
            <div class="social-icons mt-6">
                <a href="https://www.youtube.com/@U1QO1" target="_blank" aria-label="YouTube Channel">
                    <i class="fab fa-youtube"></i>
                </a>
                <a href="https://www.instagram.com/k9x9i" target="_blank" aria-label="Instagram Profile">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" aria-label="TikTok Profile">
                    <i class="fab fa-tiktok"></i>
                </a>
            </div>
        </div>
    </footer>

    <script>
        // Data for poets and poems (All content embedded directly in HTML)
        const poetsData = [
            {
                id: 'al_mutanabbi',
                name: 'أبو الطيب المتنبي',
                bio: 'هو أحمد بن الحسين الجعفي الكندي الكوفي أبو الطيب المتنبي. أحد أعظم شعراء العرب، ولد بالكوفة سنة 303 هـ وتوفي سنة 354 هـ. اشتهر بقوة لغته وفصاحته، وحكمته في شعره الذي تناول المدح والهجاء والرثاء والفخر والحكمة. يُعتبر شعره قمة الإبداع الأدبي العربي، وقد حفظ منه الكثير وصار مضرب الأمثال.',
                poems: {
                    love: [
                        { title: 'أحبك لو كان حبي داءً', text: 'أحبك لو كان حبي داءً يداويني\nوقلبي يذوبُ شوقًا، والحنينُ يكويني\nفي كلِّ نظرةٍ منكِ، أرى دنيايَ\nوفي كلِّ همسةٍ، أسمعُ لحنَ حبّي\nفأنتِ الحياةُ، وأنتِ كلُّ أمنياتي\nيا من أسرتِ فؤادي، وصرتِ نبضَ روحي' },
                        { title: 'فبتّ كأنني أسقى رضاباً', text: 'فبتّ كأنني أسقى رضاباً\nبشهدٍ من ثناياكِ الحسانِ\nوسعدُ العمرِ قد لاحَ بقلبي\nبِقربكِ، يا شفاءَ الروحِ والكيانِ\nفكمْ من ليلةٍ قد سهرتُ شوقاً\nلِألفي وجهَكِ البدرَ في الأزمانِ' }
                    ],
                    ghazal: [
                        { title: 'عيناكِ بحرٌ من الهوى', text: 'عيناكِ بحرٌ من الهوى،\nأغرقُ فيه ولا أرتوي.\nوقلبكِ جنةٌ خضراء،\nفيها روحي تهيم وتختفي.\nيا من رسمتِ الحبَّ في عينيّ،\nيا قصةَ عمري التي لا تنتهي.\nبوجودكِ تتزينُ أيامي،\nوبقربكِ تزهرُ كلُّ أزهاري.\nأنتِ النبضُ في شراييني،\nوأنتِ الحياةُ التي أرغبُ فيها.' },
                        { title: 'الثغر يبتسمُ', text: 'الثغرُ يبتسمُ،\nوالقلبُ بها يُفتتنُ، لا يرفُ.\nيا بدرَ الكمالِ أشرقَتْ،\nبينَ النجومِ، أنتِ الأجملُ، لا يخفى.\nشعركِ الليلُ، وعطركِ الفجرُ،\nوقلبكِ نهرٌ من الحنانِ، لا يجفى.\nيا آيةَ الحسنِ، يا لؤلؤةَ العصرِ،\nبكِ الحياةُ تُزهى، وبكِ الروحُ تشفى.' }
                    ],
                    wisdom: [
                        { title: 'ذو العقل يشقى في النعيم بعقله', text: 'ذو العقل يشقى في النعيم بعقله\nوأخو الجهالة في الشقاوة ينعم\nوالنفسُ راغبةٌ إذا رغّبتها\nوإذا تردّ إلى قليلٍ تقنعُ\nمن يهنْ يسهلْ الهوانُ عليه\nما لجرحٍ بميتٍ إيلامُ' },
                        { title: 'إذا أنت أكرمت الكريم ملكته', text: 'إذا أنت أكرمت الكريم ملكته\nوإن أنت أكرمت اللئيم تمردا\nفضعِ الإحسانَ في موضعهِ\nفليسَ كلُّ من يُعطى يَجودا' }
                    ],
                    joy: [
                        { title: 'عيد بأي حال عدت يا عيد', text: 'عيد بأي حال عدت يا عيد\nبما مضى أم بأمرٍ فيك تجديد\nأما الأحبة فالبيداء دونهم\nفليت دونك بيداً دونها بيد' }
                    ],
                    separation: [
                        { title: 'كفى بك داء أن ترى الموت شافيا', text: 'كفى بك داء أن ترى الموت شافيا\nوحسب المنايا أن يكن أمانيا\nوليس لي ذنب سوى أنني\nرأيت ما لم ترَ الأعينُ' }
                    ],
                    longing: [
                        { title: 'بم التعلل لا أهل ولا وطن', text: 'بم التعلل لا أهل ولا وطن\nولا نديم ولا كأس ولا سكن\nوإذا حللتُ مكاناً عزَّ مطلوبي\nفمكاني في كلِّ الأرضِ مكانُ' }
                    ]
                }
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير، معالجاً قضايا الوطن والإنسان بلغة شعرية متفردة.',
                poems: {
                    love: [
                        { title: 'غريب على الخليج', text: 'الريحُ تعوي في السواحلِ،\nوأنا غريبٌ، والقلبُ ناحلُ.\nأحملُ حباً كادَ يقتلُني،\nشوقاً لعينيكِ، وليلٍ طويلِ.' },
                        { title: 'كانت لدي وردة', text: 'كانت لدي وردة،\nسقيتها بماءِ عينيّ.\nتفتحتْ على حبٍّ،\nورفرفتْ في قلبي كطيرٍ.\nثم ذبلتْ، وماتتْ،\nكما تموتُ الأشواقُ في صمتٍ.\nيا وردتي التي رحلتْ،\nتركتِ في القلبِ جرحاً لا يندملُ.' }
                    ],
                    separation: [
                        { title: 'المومس العمياء', text: 'في الميناءِ، رياحٌ تهبُ،\nوصوتُ صراخٍ، لا يُجابُ.\nوالمومسُ العمياءُ تنتظرُ،\nفي ظلمةِ الليلِ، لا بابَ.' }
                    ],
                    longing: [
                        { title: 'رسالة إلى جيكور', text: 'يا جيكورُ، يا موطنَ الصبا،\nروحي إليكِ تحنُّ، لا تطيقُ.\nفي كلِّ ركنٍ منكِ، ذكرى،\nوعطرُ الماضي، لا يزولُ.' }
                    ],
                    wisdom: [
                        { title: 'أقوال من زمن قديم', text: 'الأيامُ دولٌ، لا تدومُ على حالٍ،\nوالعقلُ نورٌ، والجهلُ ظلامٌ.\nفكنْ حكيماً، تتبعْ دربَ الحقِّ،\nفالسعادةُ في العلمِ، لا في الأوهامِ.' }
                    ]
                }
            },
            {
                id: 'nazik_al_malaika',
                name: 'نازك الملائكة',
                bio: 'شاعرة عراقية وناقدة، ولدت في بغداد عام 1923 وتوفيت في القاهرة عام 2007. تُعد من أهم رواد الشعر الحر في الأدب العربي، تميزت قصائدها بجمال اللغة وعمق المعنى والفلسفة، وتناولت مواضيع الحرية والمرأة والحياة والموت.',
                poems: {
                    love: [
                        { title: 'أنا والليل', text: 'أنا والليلُ نجومٌ وعبيرٌ،\nوحكاياتُ حبٍّ، لا تنتهي.\nفي صمتِ الكونِ، أرواحٌ،\nتتلاقى، وتهمسُ بالحبِّ.' }
                    ],
                    separation: [
                        { title: 'شجرة القمر', text: 'شجرةُ القمرِ، وحدي أراها،\nتُظلُّ حزني، وتُحيي ذكراها.\nفي كلِّ ورقةٍ، قصةُ وداعٍ،\nوفي كلِّ غصنٍ، أنينٌ وشكوى.' }
                    ],
                    longing: [
                        { title: 'وحدة', text: 'الوحدةُ بحرٌ، والروحُ تائهةٌ،\nتبحثُ عن مرفأٍ، لا تجدُ.\nفي ظلمةِ الليلِ، أشباحٌ،\nتُلاحقُها، لا تتركُ.' }
                    ],
                    wisdom: [
                        { title: 'في الطريق', text: 'في الطريقِ، نتعلمُ الدروسَ،\nمن كلِّ خطوةٍ، نجدُ الحلولَ.\nلا تيأسْ، فالحياةُ رحلةٌ،\nفيها الصعابُ، وفيها الوصولُ.' }
                    ]
                }
            },
            {
                id: 'abd_al_wahhab',
                name: 'عبد الوهاب البياتي',
                bio: 'شاعر عراقي بارز من رواد حركة الشعر الحر، ولد في بغداد عام 1926 وتوفي في دمشق عام 1999. عرف بشعره الغزير والمتنوع الذي يجمع بين الواقعية والرمزية، ويعكس هموم الإنسان العربي وقضاياه الاجتماعية والسياسية، ويُعتبر صوته الشعري معبراً عن جيل بأكمله.',
                poems: {
                    love: [
                        { title: 'عينيها', text: 'عينيها نجمٌ، والليلُ سحرٌ،\nفيهما أغرقُ، ولا أُفيقُ.\nيا سحرَ العيونِ، يا ليلَ الحبِّ،\nفيكِ قلبي يرفرفُ، ويهفو.' }
                    ],
                    separation: [
                        { title: 'الموت في بغداد', text: 'في بغدادَ، موتٌ وزهرٌ،\nوأرواحٌ ترحلُ، لا تعودُ.\nفي كلِّ زاويةٍ، ذكرى،\nوحكاياتُ حزنٍ، لا تَبيدُ.' }
                    ],
                    longing: [
                        { title: 'رحلة في أعماق الذاكرة', text: 'في أعماقِ الذاكرةِ، رحلةٌ،\nإلى زمنٍ، لا يعودُ.\nحنينٌ يمزقُ روحي،\nوشوقٌ إليكِ، لا يهدأُ.' }
                    ],
                    wisdom: [
                        { title: 'كتاب الفقر والثورة', text: 'الفقرُ نارٌ، والثورةُ نورٌ،\nفيها نجدُ الحريةَ، وننتصرُ.\nلا تخفْ من ظلمِ الزمانِ،\nفالحقُّ أقوى، والعدلُ ينتصرُ.' }
                    ]
                }
            },
            {
                id: 'jamil_sidqi',
                name: 'جميل صدقي الزهاوي',
                bio: 'شاعر وفيلسوف عراقي، ولد في بغداد عام 1863 وتوفي فيها عام 1936. يعتبر من أبرز شعراء العراق في العصر الحديث، واشتهر بشعره الذي يدعو إلى الإصلاح الاجتماعي والنهضة والحرية، وكان من دعاة تحرير المرأة. شعره اتسم بالجرأة الفكرية والأسلوب البليغ.',
                poems: {
                    ghazal: [
                        { title: 'عيناكِ سرُّ الجمال', text: 'سحرُ العيونِ يجذبُ،\nفيها جمالٌ لا يُوصفُ.\nوالثغرُ يبتسمُ،\nوالقلبُ بها يُفتتنُ، لا يرفُ.\nيا بدرَ الكمالِ أشرقَتْ،\nبينَ النجومِ، أنتِ الأجملُ، لا يخفى.' }
                    ],
                    wisdom: [
                        { title: 'درس الحياة', text: 'الحياةُ درسٌ، والعقلُ مرآةٌ،\nفيها نرى أنفسنا، ونتعلمُ.\nلا تغترَّ بجمالٍ زائلٍ،\nفالروحُ تبقى، والجسدُ يزولُ.' }
                    ]
                }
            },
            {
                id: 'ma_ruf_al_rusafi',
                name: 'معروف الرصافي',
                bio: 'شاعر عراقي كبير، ولد في بغداد عام 1875 وتوفي فيها عام 1945. يعد من رواد الشعر الحديث في العراق، وعرف بشعره الوطني والاجتماعي الذي يلامس قضايا الفقر والجهل والظلم، وكان له دور كبير في الصحافة العراقية، داعياً للعدالة والتعليم ومناهضة الاستبداد.',
                poems: {
                    love: [
                        { title: 'أنت الحبيب', text: 'أنتَ الحبيبُ، ونورُ عينيّ،\nفي كلِّ نبضٍ، أنتَ تسكُنُ.\nيا من أسرتَ قلبي،\nوروحي إليكَ، لا تفارقُ.' }
                    ],
                    wisdom: [
                        { title: 'الحياة دروس', text: 'في كلِّ يومٍ درسٌ،\nمنها نتعلمُ ونتقنُ.\nفاصبرْ على حكمها،\nواعملْ بجدٍّ، فكلُّ شيءٍ يتقنُ.\nالحياةُ بحرٌ عميقٌ،\nوالعقلُ سفينتُكَ، فكنْ حكيماً، لا تهنْ.' }
                    ]
                }
            },
            {
                id: 'mohammad_mahdi_al_jawahiri',
                name: 'محمد مهدي الجواهري',
                bio: 'شاعر عربي عراقي يُلقب بـ "نهر العراق الثالث" و "شاعر العرب الأكبر". ولد في النجف عام 1899 وتوفي في دمشق عام 1997. يعتبر من أبرز شعراء العصر الحديث، وامتاز بغزارة إنتاجه وقوة أسلوبه وشاعريته الفذة التي غطت مختلف الأغراض الشعرية من وطنية وقومية ووجدانية.',
                poems: {
                    love: [
                        { title: 'أتتني ذات يوم', text: 'أتتني ذات يومٍ، كالبدرِ،\nوالكونُ يرقصُ، والروحُ تسهرُ.\nفي عينيها، سحرٌ خفيٌ،\nوقلبٌ ينبضُ، لا يُنكرُ.' }
                    ],
                    wisdom: [
                        { title: 'كن في الحياة', text: 'كن في الحياةِ كالنهرِ، يجري،\nلا يتوقفُ، ولا يتوانى.\nفالزمنُ يمضي، لا ينتظرُ،\nوالعمرُ يمرُّ، لا يتوانى.' }
                    ]
                }
            },
            {
                id: 'lamia_abbas_amara',
                name: 'لميعة عباس عمارة',
                bio: 'شاعرة عراقية رائدة، ولدت في بغداد عام 1929. تُعد من أبرز شاعرات العراق في العصر الحديث، وامتازت قصائدها بالجرأة والجمال والرقة، وتناولت مواضيع الحب والمرأة والوطن بأسلوبها الخاص المميز.',
                poems: {
                    love: [
                        { title: 'لا أريد شيئًا سوى الحب', text: 'لا أريد شيئًا سوى الحب،\nفهو نبضُ الحياةِ، وروحُ الكونِ.\nفي كلِّ زاويةٍ، أجدُكَ،\nوفي كلِّ لحظةٍ، أنتَ حاضرٌ.' }
                    ],
                    longing: [
                        { title: 'أشتاق إلى بغداد', text: 'أشتاقُ إلى بغدادَ، إلى شوارعها،\nإلى أزقتها، ونسائمِها.\nيا مدينةَ العشاقِ، يا بغدادُ،\nقلبي إليكِ يحنُّ، لا ينامُ.' }
                    ]
                }
            },
            {
                id: 'mustafa_jamal_al_din',
                name: 'مصطفى جمال الدين',
                bio: 'شاعر عراقي معاصر، ولد في النجف عام 1927 وتوفي في دمشق عام 1996. كان أستاذاً جامعياً وباحثاً لغوياً، وعرف بشعره الذي يجمع بين الأصالة والمعاصرة، وتميز بأسلوبه السلس والجميل، وله العديد من الدواوين الشعرية التي تتناول مواضيع وطنية واجتماعية.',
                poems: {
                    love: [
                        { title: 'على شاطئ عينيك', text: 'على شاطئِ عينيكِ، ألتقي روحي،\nأجدُ فيها الحبَّ، وملاذَ الروحِ.' }
                    ],
                    wisdom: [
                        { title: 'العلم سلاح', text: 'العلمُ نورٌ، والجهلُ ظلامٌ،\nبهِ الأممُ ترتقي، وترفعُ الهامَ.\nسلاحٌ في يدِ العقلِ،\nيفتحُ الآفاقَ، ويُزيلُ الأوهامَ.' }
                    ]
                }
            },
            {
                id: 'abdul_razzaq_abdul_wahid',
                name: 'عبد الرزاق عبد الواحد',
                bio: 'شاعر عراقي كبير، ولد عام 1930 في ميسان. يُعرف بشعره الوطني الذي يمجد العراق وتاريخه، وبأسلوبه الملحمي القوي. كان له دور بارز في الحركة الشعرية العراقية المعاصرة، ونال العديد من الجوائز تقديرًا لمسيرته الشعرية.',
                poems: {
                    love: [
                        { title: 'أحببتكِ جداً', text: 'أحببتكِ جداً، حتى صارَ الحبُّ... جزءاً من روحي، لا يفارقُني.' }
                    ],
                    wisdom: [
                        { title: 'رسالة إلى الجيل', text: 'يا جيلَ المستقبلِ، كنْ قوياً... بالعلمِ والعملِ، ترفعْ الهممَ.' }
                    ],
                    separation: [
                        { title: 'بغداد الحزينة', text: 'يا بغدادُ، حزنٌ يملأُ الفؤادَ... على فراقٍ، لا ينسى.' }
                    ],
                    longing: [
                        { title: 'شوق العودة', text: 'شوقٌ إلى الوطنِ، يمزقُ الروحَ... حنينٌ إلى الأهلِ، لا يهدأُ.' }
                    ],
                    ghazal: [
                        { title: 'يا أجمل من في الوجود', text: 'يا أجملَ من في الوجودِ، يا قمري... سحرُ عينيكِ، يُذيبُ القلبَ.' }
                    ],
                    joy: [
                        { title: 'فرحة الانتصار', text: 'فرحةُ الانتصارِ، تملأُ الكونُ... بصيحاتِ الفرحِ، تُرنّمُ الروحُ.' }
                    ]
                }
            },
            {
                id: 'ali_al_shalah',
                name: 'علي الشلاه',
                bio: 'شاعر عراقي معاصر، وأكاديمي، وكاتب. يُعرف بأسلوبه الشعري المتميز الذي يجمع بين الفصحى والعامية، ويتناول قضايا اجتماعية وسياسية ووجدانية. له مساهمات فعالة في الثقافة العراقية والعربية.',
                poems: {
                    love: [
                        { title: 'همسة حب', text: 'همسةُ حبٍّ، في أذنِ الليلِ... تُحيي الروحَ، وتُنيرُ الدربَ.' }
                    ],
                    wisdom: [
                        { title: 'درس من الحياة', text: 'الحياةُ مدرسةٌ، نتعلمُ منها... في كلِّ يومٍ، درساً جديداً.' }
                    ],
                     separation: [
                        { title: 'وداعٌ صامت', text: 'وداعٌ صامتٌ، والدمعُ يجري... على خدودٍ، لا تجفُّ.' }
                    ],
                    longing: [
                        { title: 'حنين الأمس', text: 'حنينُ الأمسِ، يزورُني ليلاً... يوقظُ فيّ الشوقَ، والأحزانَ.' }
                    ],
                    ghazal: [
                        { title: 'عن العيون الساحرة', text: 'عيناكِ سحرٌ، والرموشُ سهامٌ... تصيبُ القلبَ، لا تخطئُ.' }
                    ],
                    joy: [
                        { title: 'ضحكة أمل', text: 'ضحكةُ أملٍ، تُنيرُ الدروبَ... تُبعدُ اليأسَ، وتُحيي القلوبَ.' }
                    ]
                }
            }
            // Add more poets as needed to enrich the content
        ];

        // DOM Elements
        const mainHeader = document.getElementById('main-header');
        const searchInput = document.getElementById('search-input');
        const hamburgerMenuToggle = document.getElementById('hamburger-menu-toggle');
        const mobileSidebar = document.getElementById('mobile-sidebar');
        const contentSections = document.querySelectorAll('.content-section');

        const poetsGrid = document.getElementById('poets-grid');
        const poetDetailPage = document.getElementById('poet-detail-page'); // Renamed from modal
        const poetDetailNameDisplay = document.getElementById('poet-detail-name-display'); // Renamed for clarity
        const poetDetailBioDisplay = document.getElementById('poet-detail-bio-display'); // Renamed for clarity
        const poemCategoriesContainer = document.getElementById('poem-categories');
        const poemsDisplay = document.getElementById('poems-display'); // Where poems (full text) will be shown

        let currentPoet = null; // Stores the currently selected poet object

        // --- Header Sticky and Hide/Show on Scroll ---
        let lastScrollTop = 0;
        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            if (scrollTop > lastScrollTop && scrollTop > mainHeader.offsetHeight) {
                mainHeader.classList.add('header-hidden');
            } else {
                mainHeader.classList.remove('header-hidden');
            }
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop;
        });

        // --- Mobile Sidebar Toggle ---
        hamburgerMenuToggle.addEventListener('click', () => {
            mobileSidebar.classList.add('open');
        });

        function closeMobileMenu() {
            mobileSidebar.classList.remove('open');
        }

        // Close sidebar if clicking outside of it
        window.addEventListener('click', (event) => {
            if (mobileSidebar.classList.contains('open') && !mobileSidebar.contains(event.target) && event.target !== hamburgerMenuToggle && !hamburgerMenuToggle.contains(event.target)) {
                closeMobileMenu();
            }
        });

        // --- Section Switching Logic ---
        function showSection(sectionId) {
            // Hide all content sections initially
            contentSections.forEach(section => {
                section.classList.remove('active');
                section.classList.add('hidden'); // Ensure it's hidden
            });

            // Show the target section
            const targetSection = document.getElementById(`${sectionId}-section`);
            if (targetSection) {
                targetSection.classList.remove('hidden');
                // Use setTimeout to allow CSS transition to apply after display:block
                setTimeout(() => {
                    targetSection.classList.add('active');
                }, 10);
            }

            closeMobileMenu(); // Ensure mobile menu closes
            // Scroll to the top of the content area, accounting for fixed header
            window.scrollTo({ top: mainHeader.offsetHeight, behavior: 'smooth' });
        }

        // Attach event listeners to mobile navigation links (as they are the primary nav)
        mobileSidebar.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', (event) => {
                event.preventDefault(); // Prevent default link behavior
                showSection(link.dataset.section);
            });
        });

        // --- Poet Grid Rendering ---
        function renderPoetsGrid(poetsToDisplay) {
            poetsGrid.innerHTML = ''; // Clear existing poets
            if (poetsToDisplay.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-xl text-body-text">لا توجد نتائج مطابقة.</p>';
                return;
            }

            poetsToDisplay.forEach(poet => {
                const poetCard = document.createElement('div');
                poetCard.classList.add('poet-grid-card');
                poetCard.innerHTML = `<h3>${poet.name}</h3>`;
                poetCard.addEventListener('click', () => {
                    displayPoetDetailPage(poet);
                });
                poetsGrid.appendChild(poetCard);
            });
        }

        // --- Search Functionality (for poets grid on main page) ---
        searchInput.addEventListener('input', () => {
            const searchTerm = searchInput.value.trim().toLowerCase();
            const filteredPoets = poetsData.filter(poet =>
                poet.name.toLowerCase().includes(searchTerm)
            );
            renderPoetsGrid(filteredPoets);
            showSection('poets'); // Ensure poets section is visible when searching
        });


        // --- Display Poet Detail Page (The "Second Layer") ---
        function displayPoetDetailPage(poet) {
            currentPoet = poet; // Set the current poet
            poetDetailNameDisplay.textContent = poet.name;
            poetDetailBioDisplay.textContent = poet.bio;
            renderPoemCategories(poet.poems); // Render category buttons

            showSection('poet-detail'); // Switch to poet detail page section
            window.scrollTo({ top: mainHeader.offsetHeight, behavior: 'smooth' }); // Scroll to top of the new page
        }

        // Render Poem Categories on Poet Detail Page
        function renderPoemCategories(poemsByCategories) {
            poemCategoriesContainer.innerHTML = ''; // Clear previous categories
            const categories = Object.keys(poemsByCategories);

            const categoryMap = {
                'love': 'الحب',
                'ghazal': 'الغزل',
                'wisdom': 'الحكمة',
                'joy': 'الفرح',
                'separation': 'الفراق',
                'longing': 'الحنين',
            };

            // Define a preferred order for categories
            const orderedCategories = ['love', 'ghazal', 'wisdom', 'joy', 'separation', 'longing'];
            const displayedCategories = orderedCategories.filter(cat => categories.includes(cat) && poemsByCategories[cat].length > 0); // Only show categories with poems

            if (displayedCategories.length === 0) {
                 poemCategoriesContainer.innerHTML = '<p class="text-center text-body-text">لا توجد فئات قصائد متاحة لهذا الشاعر.</p>';
                 poemsDisplay.innerHTML = ''; // Clear poems display too
                 return;
            }

            displayedCategories.forEach(categoryKey => {
                const button = document.createElement('button');
                button.classList.add('category-pill');
                button.textContent = categoryMap[categoryKey] || categoryKey; // Use Arabic name if mapped
                button.dataset.category = categoryKey;
                button.addEventListener('click', () => {
                    displayPoemsForCategory(categoryKey);
                    // Set active class
                    poemCategoriesContainer.querySelectorAll('.category-pill').forEach(btn => btn.classList.remove('active'));
                    button.classList.add('active');
                });
                poemCategoriesContainer.appendChild(button);
            });

            // Automatically click the first category to show poems on page load/poet selection
            if (displayedCategories.length > 0) {
                // Use a slight delay to ensure categories are rendered before click
                setTimeout(() => {
                    poemCategoriesContainer.querySelector(`[data-category="${displayedCategories[0]}"]`).click();
                }, 50);
            }
        }

        // Display Poems for a Category (Full Text Directly) on Poet Detail Page
        function displayPoemsForCategory(category) {
            poemsDisplay.innerHTML = ''; // Clear previous poems
            if (!currentPoet || !currentPoet.poems[category] || currentPoet.poems[category].length === 0) {
                poemsDisplay.innerHTML = '<p class="text-center text-body-text">لا توجد قصائد في هذه الفئة.</p>';
                return;
            }

            const poems = currentPoet.poems[category];
            poems.forEach((poem, index) => {
                const poemCard = document.createElement('div');
                poemCard.classList.add('poem-full-card');
                poemCard.id = `poem-card-${currentPoet.id}-${category}-${index}`; // Unique ID for copy
                poemCard.innerHTML = `
                    <h4>${poem.title}</h4>
                    <p class="poem-text">${poem.text}</p>
                    <button class="copy-button" onclick="copyPoemToClipboard('${poemCard.id}')">
                        <i class="fas fa-copy"></i> نسخ
                    </button>
                `;
                poemsDisplay.appendChild(poemCard);
            });
        }

        // --- Copy to Clipboard Function ---
        function copyPoemToClipboard(cardId) {
            const poemCard = document.getElementById(cardId);
            const poemTitle = poemCard.querySelector('h4').innerText;
            const poemText = poemCard.querySelector('.poem-text').innerText;
            const fullTextToCopy = `${poemTitle}\n\n${poemText}\n\n[موسوعة الشعر العراقي]`;

            const tempTextArea = document.createElement('textarea');
            tempTextArea.value = fullTextToCopy;
            document.body.appendChild(tempTextArea);
            tempTextArea.select();
            document.execCommand('copy');
            document.body.removeChild(tempTextArea);

            // Give visual feedback
            const copyButton = poemCard.querySelector('.copy-button');
            const originalText = copyButton.innerHTML;
            copyButton.innerHTML = '<i class="fas fa-check"></i> تم النسخ!';
            copyButton.style.backgroundColor = '#4CAF50'; // Green for success

            setTimeout(() => {
                copyButton.innerHTML = originalText;
                copyButton.style.backgroundColor = 'var(--copy-button-bg)';
            }, 1500);
        }

        // --- Initial Load ---
        window.onload = () => {
            document.getElementById('current-year-footer').textContent = new Date().getFullYear();
            showSection('home'); // Show home section by default
            renderPoetsGrid(poetsData); // Populate the poets grid initially
        };
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for icons (Hamburger, Social Media, Search) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Custom Colors and Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap'); /* Modern Arabic font */
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* Classic Arabic font for poem text */

        :root {
            --main-bg: #FFF2E0; /* Light cream background for the entire site */
            --dark-heading: #222222;
            --body-text: #444444;
            --accent-orange: #FFA500; /* Soft orange for accents */
            --accent-brown: #8B5E3C; /* Warm brown for accents */
            --footer-bg: #222831; /* Dark background for footer, as per previous image */
            --footer-text: #EEEEEE; /* Light text for footer */
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

        /* Search Bar within Header */
        .header-search-container {
            flex-grow: 1; /* Allow search bar to take available space */
            margin: 0 1rem; /* Space between title and hamburger */
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
            transition: color 0.2s ease;
        }
        .hamburger-toggle:hover {
            color: var(--accent-orange);
        }

        /* --- Hero Section Animations --- */
        .hero-text {
            opacity: 0;
            transform: translateY(20px);
            animation-fill-mode: forwards;
        }
        .hero-text:first-child { animation: slideInUp 0.8s ease-out 0.2s; }
        .hero-text:last-child { animation: slideInUp 0.8s ease-out 0.4s; }

        @keyframes slideInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- Content Section General Styles --- */
        .content-section {
            display: none; /* Hidden by default */
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
            padding-top: 2rem;
            padding-bottom: 2rem;
        }
        .content-section.active {
            display: block; /* Show when active */
            opacity: 1;
            transform: translateY(0);
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
            border-top: 5px solid var(--accent-brown);
            position: relative;
            overflow: hidden;
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
            margin-bottom: 0;
        }

        /* --- Poet Detail Modal --- */
        .poet-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6); /* Darker overlay for strong layering effect */
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        .poet-modal.open {
            opacity: 1;
            visibility: visible;
        }
        .poet-modal-content {
            background-color: var(--main-bg);
            border-radius: 15px;
            padding: 2.5rem;
            width: 90%;
            max-width: 900px;
            max-height: 90vh; /* Limit height for scrolling */
            overflow-y: auto;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
            position: relative;
            transform: translateY(30px); /* Appear from slightly below */
            opacity: 0;
            transition: transform 0.4s ease-out, opacity 0.4s ease-out;
        }
        .poet-modal.open .poet-modal-content {
            transform: translateY(0);
            opacity: 1;
        }
        .close-modal-btn {
            position: absolute;
            top: 15px;
            left: 15px; /* Position from left in RTL */
            font-size: 2.5rem;
            color: var(--dark-heading);
            cursor: pointer;
            transition: color 0.2s ease;
        }
        .close-modal-btn:hover {
            color: var(--accent-orange);
        }

        /* Poet Detail Content */
        #poet-detail-name {
            font-size: 3rem;
            font-weight: 800;
            color: var(--dark-heading);
            margin-bottom: 1.5rem;
            text-align: center;
            border-bottom: 2px solid var(--accent-orange); /* Underline for name */
            padding-bottom: 10px;
        }
        #poet-detail-bio {
            font-size: 1.1rem;
            color: var(--body-text);
            line-height: 2;
            margin-bottom: 2.5rem;
            padding: 0 1rem;
            text-align: justify;
        }

        /* Category Buttons within Modal */
        .category-pill {
            background-color: var(--accent-orange);
            color: white;
            padding: 0.75rem 1.5rem;
            border-radius: 9999px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .category-pill:hover {
            background-color: var(--accent-brown);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        .category-pill.active {
            background-color: var(--accent-brown);
            transform: translateY(-1px);
        }

        /* Individual Poem Display (Full Text Directly) within Modal */
        .poem-full-card {
            background-color: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            margin-bottom: 1.5rem;
            border-right: 4px solid var(--accent-orange); /* Artistic border */
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
        }

        /* --- Floating "Back to Home" Button --- */
        #back-to-home-btn {
            position: fixed;
            top: 100px; /* Below the header */
            right: 20px;
            background-color: var(--accent-brown);
            color: white;
            padding: 12px 20px;
            border-radius: 9999px;
            font-weight: 700;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            z-index: 40;
            opacity: 0;
            visibility: hidden;
        }
        #back-to-home-btn.active {
            opacity: 1;
            visibility: visible;
            transform: translateX(0);
        }
        #back-to-home-btn:hover {
            background-color: var(--accent-orange);
            transform: translateY(-2px);
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
            display: flex; /* Use flex to align children */
            flex-direction: column;
            align-items: center; /* Center items horizontally */
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
            width: 100%; /* Make links full width inside sidebar */
            text-align: center; /* Center text */
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        #mobile-sidebar a:last-child {
            border-bottom: none; /* No border for the last item */
        }
        #mobile-sidebar a:hover {
            background-color: rgba(255,255,255,0.1);
        }
        #mobile-sidebar .close-btn {
            position: absolute;
            top: 10px;
            left: 20px; /* Adjusted for RTL */
            font-size: 2.5rem;
            color: white;
            cursor: pointer;
        }

        /* --- Responsive Adjustments --- */
        @media (max-width: 768px) {
            .fixed-header {
                flex-wrap: wrap;
                padding: 1rem;
                justify-content: center; /* Center items on small screens */
            }
            .fixed-header h1 {
                width: 100%;
                text-align: center;
                margin-bottom: 0.5rem;
            }
            .header-search-container {
                order: 1; /* Place search bar below title */
                margin: 0.5rem 0; /* Add vertical margin */
                width: calc(100% - 60px); /* Adjust width to make space for hamburger */
            }
            .hamburger-toggle {
                position: absolute;
                left: 1rem;
                top: 1rem;
            }
            .nav-links {
                display: none !important; /* Hide desktop nav on small screens */
            }

            .hero-headline { font-size: 3rem; }
            .hero-subheading { font-size: 1.4rem; }

            .poet-grid-card h3 { font-size: 1.8rem; }

            .poet-modal-content {
                width: 95%;
                padding: 1.5rem;
            }
            #poet-detail-name { font-size: 2.2rem; }
            #poet-detail-bio { font-size: 1rem; }
            .category-pill { padding: 0.6rem 1rem; font-size: 0.9rem; }
            .poem-full-card h4 { font-size: 1.5rem; }
            .poem-full-card .poem-text { font-size: 1rem; }

            #back-to-home-btn {
                top: 80px; /* Adjust for smaller header height */
                padding: 10px 15px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <!-- Top Header (Fixed Navigation Bar) -->
    <header id="main-header" class="fixed-header">
        <!-- Website Title -->
        <h1 class="text-3xl sm:text-4xl font-extrabold text-accent-brown whitespace-nowrap">موسوعة الشعر العراقي</h1>

        <!-- Search Bar -->
        <div class="header-search-container relative">
            <input type="text" id="search-input" placeholder="ابحث عن شاعر أو قصيدة..." class="header-search-input">
            <i class="fas fa-search header-search-icon"></i>
        </div>

        <!-- Hamburger Menu Toggle -->
        <button id="hamburger-menu-toggle" class="hamburger-toggle">
            <i class="fas fa-bars"></i>
        </button>

        <!-- Desktop Navigation Links (Hidden on Mobile, controlled by JS for header-hidden) -->
        <nav class="nav-links hidden md:flex space-x-3 space-x-reverse">
            <button class="nav-btn active" data-section="home">الصفحة الرئيسية</button>
            <button class="nav-btn" data-section="poets">الشعراء</button>
            <button class="nav-btn" data-section="love">الحب</button>
            <button class="nav-btn" data-section="separation">الفراق</button>
            <button class="nav-btn" data-section="longing">الحنين</button>
            <button class="nav-btn" data-section="ghazal">الغزل</button>
            <button class="nav-btn" data-section="wisdom">الحكمة</button>
        </nav>
    </header>

    <!-- Mobile Sidebar Menu -->
    <div id="mobile-sidebar">
        <button class="close-btn" onclick="closeMobileMenu()">&times;</button>
        <a href="#" data-section="home">الصفحة الرئيسية</a>
        <a href="#" data-section="poets">الشعراء</a>
        <a href="#" data-section="love">الحب</a>
        <a href="#" data-section="separation">الفراق</a>
        <a href="#" data-section="longing">الحنين</a>
        <a href="#" data-section="ghazal">الغزل</a>
        <a href="#" data-section="wisdom">الحكمة</a>
    </div>

    <!-- Main Content Area -->
    <main class="container mx-auto px-4">
        <!-- Offset for fixed header -->
        <div class="h-[100px] sm:h-[100px] md:h-[80px]"></div>

        <!-- Hero Section -->
        <section id="home-section" class="content-section active text-center py-20 sm:py-24">
            <h2 class="hero-text text-4xl sm:text-5xl lg:text-6xl font-extrabold text-dark-heading mb-6 leading-tight">
                مرحبًا بك في موسوعة الشعر العراقي
            </h2>
            <p class="hero-text text-lg sm:text-xl lg:text-2xl text-body-text mb-10 max-w-3xl mx-auto leading-relaxed">
                بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين
            </p>
        </section>

        <!-- Poets Section (Grid of Names) -->
        <section id="poets-section" class="content-section py-10 sm:py-16">
            <h2 class="text-4xl font-bold text-dark-heading text-center mb-10">الشعراء</h2>
            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <!-- Poet cards will be dynamically generated here by JS -->
            </div>
        </section>

        <!-- Floating "Back to Home" Button -->
        <button id="back-to-home-btn" class="hidden" onclick="showSection('home'); closePoetModal();">
            العودة للصفحة الرئيسية
        </button>
    </main>

    <!-- Poet Detail Modal/Layer -->
    <div id="poet-detail-modal" class="poet-modal">
        <div class="poet-modal-content">
            <button class="close-modal-btn" onclick="closePoetModal()">&times;</button>
            <h2 id="poet-detail-name"></h2>
            <p id="poet-detail-bio"></p>

            <h3 class="text-3xl font-bold text-dark-heading text-center mb-6 mt-8">قصائد الشاعر</h3>
            <div id="poem-categories" class="flex flex-wrap justify-center gap-3 mb-8">
                <!-- Category buttons will be generated here -->
            </div>
            <div id="poems-display">
                <!-- Poems with title and full text will load directly here -->
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-footer-bg py-8 text-center mt-10">
        <div class="container mx-auto px-4">
            <h4 class="text-footer-text text-3xl sm:text-4xl font-extrabold mb-4">موسوعة الشعر العراقي</h4>
            <p class="text-footer-text text-base leading-relaxed max-w-4xl mx-auto mb-6">
                بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي من عمالقة الشعر إلى الأصوات الشابة. نسعى لإثراء الساحة الأدبية وتقديم أرشيف متكامل يعكس جمال وعمق الكلمة العراقية.
            </p>
            <p class="text-footer-text text-sm mb-4">
                &copy; <span id="current-year"></span> كرار حيدر. جميع الحقوق محفوظة.
            </p>
            <div class="flex flex-col sm:flex-row justify-center items-center sm:space-x-8 space-y-4 sm:space-y-0 text-2xl text-footer-text">
                <a href="https://www.youtube.com/@U1QO1" target="_blank" class="hover:text-accent-orange transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-youtube"></i> <span>@U1QO1</span>
                </a>
                <a href="https://www.instagram.com/k9x9i" target="_blank" class="hover:text-accent-orange transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-instagram"></i> <span>@k9x9i</span>
                </a>
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" class="hover:text-accent-orange transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-tiktok"></i> <span>@c3_i2</span>
                </a>
            </div>
            <div class="text-footer-text text-sm mt-6 flex flex-wrap justify-center gap-x-4 gap-y-2">
                <a href="#" class="hover:underline">سياسة الخصوصية</a>
                <span>|</span>
                <a href="#" class="hover:underline">شروط الاستخدام</a>
                <span>|</span>
                <a href="#" class="hover:underline">خريطة الموقع</a>
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
        const desktopNavButtons = document.querySelectorAll('.nav-links .nav-btn');
        const mobileNavLinks = document.querySelectorAll('#mobile-sidebar a');
        const contentSections = document.querySelectorAll('.content-section');

        const poetsGrid = document.getElementById('poets-grid');
        const poetDetailModal = document.getElementById('poet-detail-modal');
        const poetDetailName = document.getElementById('poet-detail-name');
        const poetDetailBio = document.getElementById('poet-detail-bio');
        const poemCategoriesContainer = document.getElementById('poem-categories');
        const poemsDisplay = document.getElementById('poems-display'); // Where poems (full text) will be shown
        const backToHomeBtn = document.getElementById('back-to-home-btn');

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
            // Hide all sections
            contentSections.forEach(section => {
                section.classList.remove('active');
            });
            // Show the selected section
            const targetSection = document.getElementById(`${sectionId}-section`);
            if (targetSection) {
                targetSection.classList.add('active');
            }

            // Update active state for desktop nav buttons
            desktopNavButtons.forEach(button => {
                if (button.dataset.section === sectionId) {
                    button.classList.add('active');
                } else {
                    button.classList.remove('active');
                }
            });

            // Hide the back-to-home button if on home or poets overview
            if (sectionId === 'home' || sectionId === 'poets') {
                backToHomeBtn.classList.remove('active');
            } else {
                // This button should only be active if the poet modal is *not* open
                // The poet modal itself handles its own back button logic to some extent
                // For direct navigation to categories from header, it should be active.
                backToHomeBtn.classList.add('active');
            }

            // Scroll to the top of the content area
            window.scrollTo({ top: mainHeader.offsetHeight, behavior: 'smooth' });
            closeMobileMenu(); // Ensure mobile menu closes
        }

        // Attach event listeners to desktop navigation buttons
        desktopNavButtons.forEach(button => {
            button.addEventListener('click', () => showSection(button.dataset.section));
        });

        // Attach event listeners to mobile navigation links
        mobileNavLinks.forEach(link => {
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
                poetCard.addEventListener('click', () => openPoetModal(poet));
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
        });

        // --- Poet Detail Modal Logic ---
        function openPoetModal(poet) {
            currentPoet = poet; // Set the current poet
            poetDetailName.textContent = poet.name;
            poetDetailBio.textContent = poet.bio;
            renderPoemCategories(poet.poems);
            poetDetailModal.classList.add('open');
            document.body.style.overflow = 'hidden'; // Prevent scrolling body when modal is open
            backToHomeBtn.classList.add('active'); // Show floating button
        }

        function closePoetModal() {
            poetDetailModal.classList.remove('open');
            document.body.style.overflow = ''; // Restore body scrolling
            backToHomeBtn.classList.remove('active'); // Hide floating button
        }

        // Render Poem Categories in Modal
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
                 poemsDisplay.innerHTML = '';
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

            // Automatically click the first category to show poems on modal open
            if (displayedCategories.length > 0) {
                // Use a slight delay to ensure categories are rendered before click
                setTimeout(() => {
                    poemCategoriesContainer.querySelector(`[data-category="${displayedCategories[0]}"]`).click();
                }, 50);
            }
        }

        // Display Poems for a Category (Full Text Directly) within Modal
        function displayPoemsForCategory(category) {
            poemsDisplay.innerHTML = ''; // Clear previous poems
            if (!currentPoet || !currentPoet.poems[category] || currentPoet.poems[category].length === 0) {
                poemsDisplay.innerHTML = '<p class="text-center text-body-text">لا توجد قصائد في هذه الفئة.</p>';
                return;
            }

            const poems = currentPoet.poems[category];
            poems.forEach(poem => {
                const poemCard = document.createElement('div');
                poemCard.classList.add('poem-full-card');
                poemCard.innerHTML = `
                    <h4>${poem.title}</h4>
                    <p class="poem-text">${poem.text}</p>
                `;
                poemsDisplay.appendChild(poemCard);
            });
        }

        // --- Initial Load ---
        window.onload = () => {
            document.getElementById('current-year').textContent = new Date().getFullYear();
            showSection('home'); // Show home section by default
            renderPoetsGrid(poetsData); // Populate the poets grid initially
        };
    </script>
</body>
</html>

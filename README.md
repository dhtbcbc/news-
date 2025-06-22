<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Custom Colors and Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap');

        :root {
            --main-bg: #FFF2E0;
            --dark-heading: #222222;
            --body-text: #444444;
            --button-default-text: #000000;
            --button-bg-default: #E0E0E0;
            --button-hover-bg: #FFA500;
            --button-hover-text: white;
            --footer-text: #EEEEEE;
            --dark-blue-footer: #1A2B4C;
            --footer-link-hover: #FFA500;
            --poet-card-border: #8B5E3C;
            --modal-bg: #FFF2E0;
            --copy-button-bg: #00ADB5;
            --copy-button-hover-bg: #008C99;
            --accent-orange: #FFA500;
            --accent-brown: #8B5E3C;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--main-bg);
            color: var(--body-text);
            line-height: 1.8;
            scroll-behavior: smooth;
            overflow-x: hidden;
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

        /* Header Styles */
        .fixed-header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 50;
            background-color: var(--main-bg);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            padding: 1rem 1.5rem;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .header-hidden {
            transform: translateY(-100%);
        }

        .header-title {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--dark-heading);
            white-space: nowrap;
            flex-shrink: 0;
            margin-left: 1rem;
        }

        .header-search-container {
            flex-grow: 1;
            position: relative;
        }
        .header-search-input {
            width: 100%;
            padding: 0.75rem 1rem 0.75rem 2.5rem;
            border-radius: 9999px;
            border: 2px solid var(--accent-orange);
            background-color: white;
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
            box-shadow: 0 0 0 3px rgba(139, 94, 60, 0.2);
        }
        .header-search-icon {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--body-text);
            font-size: 1.1rem;
        }

        .hamburger-toggle {
            color: var(--dark-heading);
            font-size: 2.2rem;
            cursor: pointer;
            padding: 0.5rem;
            transition: color 0.2s ease;
            flex-shrink: 0;
            margin-right: 0.5rem;
        }
        .hamburger-toggle:hover {
            color: var(--accent-orange);
        }

        /* Hero Section */
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

        /* Poet Grid Card */
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
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 150px;
        }
        .poet-grid-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
            background-color: #FFFBF5;
        }
        .poet-grid-card h3 {
            color: var(--dark-heading);
            font-size: 2rem;
            font-weight: 700;
            margin: 0;
            transition: color 0.2s ease;
        }
        .poet-grid-card:hover h3 {
            color: var(--accent-orange);
        }

        /* Poet Detail Page */
        .poet-detail-page {
            display: none;
            padding: 2rem 1rem;
        }
        .poet-detail-content {
            background-color: white;
            border-radius: 15px;
            padding: 2.5rem;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
        }
        #poet-detail-name {
            font-size: 3rem;
            font-weight: 800;
            color: var(--dark-heading);
            margin-bottom: 1.5rem;
            text-align: center;
            border-bottom: 2px solid var(--accent-orange);
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

        /* Category Buttons */
        .category-pill {
            background-color: var(--button-bg-default);
            color: var(--button-default-text);
            padding: 0.75rem 1.5rem;
            border-radius: 9999px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .category-pill:hover, .category-pill.active {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-text);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        /* Poem Cards */
        .poem-full-card {
            background-color: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            margin-bottom: 1.5rem;
            border-right: 4px solid var(--accent-orange);
            position: relative;
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
            font-family: 'Amiri', serif;
            font-size: 1.1rem;
            white-space: pre-line;
            line-height: 2.2;
            color: var(--body-text);
            text-align: justify;
            padding-bottom: 1.5rem;
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

        /* Back Button */
        .back-button {
            display: flex;
            align-items: center;
            color: var(--accent-orange);
            font-weight: 600;
            margin-bottom: 1.5rem;
            cursor: pointer;
            transition: color 0.2s ease;
        }
        .back-button:hover {
            color: var(--accent-brown);
        }
        .back-button i {
            margin-left: 0.5rem;
        }

        /* Mobile Sidebar */
        #mobile-sidebar {
            position: fixed;
            top: 0;
            right: -250px;
            width: 250px;
            height: 100%;
            background-color: var(--accent-brown);
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

        /* Footer */
        .site-footer {
            background-color: var(--dark-blue-footer);
            color: var(--footer-text);
            padding: 2rem 0;
            text-align: center;
            margin-top: 4rem;
        }
        .site-footer a {
            color: var(--footer-text);
            transition: color 0.2s ease;
        }
        .site-footer a:hover {
            color: var(--footer-link-hover);
        }

        /* Responsive Adjustments */
        @media (max-width: 768px) {
            .fixed-header {
                flex-wrap: wrap;
                padding: 0.8rem 1rem;
            }
            .header-title {
                width: 100%;
                text-align: center;
                margin-bottom: 0.5rem;
                font-size: 1.8rem;
                order: -1;
            }
            .header-search-container {
                width: calc(100% - 60px);
                margin: 0.5rem 0;
            }
            .hamburger-toggle {
                position: absolute;
                left: 1rem;
                top: 0.8rem;
            }

            .hero-section { padding: 3rem 1rem; }
            .hero-title { font-size: 2.5rem; }
            .hero-subtitle { font-size: 1.2rem; }

            .poet-grid-card h3 { font-size: 1.6rem; }

            .poet-detail-content { padding: 1.5rem; }
            #poet-detail-name { font-size: 2rem; margin-bottom: 1rem; }
            #poet-detail-bio { font-size: 0.95rem; line-height: 1.8; margin-bottom: 1.5rem; padding: 0;}
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
        }
    </style>
</head>
<body>
    <!-- Top Header -->
    <header id="main-header" class="fixed-header">
        <h1 class="header-title">موسوعة الشعر العراقي</h1>

        <div class="header-search-container relative">
            <input type="text" id="search-input" placeholder="ابحث عن شاعر أو قصيدة..." class="header-search-input">
            <i class="fas fa-search header-search-icon"></i>
        </div>

        <button id="hamburger-menu-toggle" class="hamburger-toggle">
            <i class="fas fa-bars"></i>
        </button>
    </header>

    <!-- Mobile Sidebar Menu -->
    <div id="mobile-sidebar">
        <button class="close-btn" onclick="closeMobileMenu()">&times;</button>
        <a href="#" onclick="showHomePage()">الصفحة الرئيسية</a>
        <a href="#" onclick="showPoetsPage()">الشعراء</a>
        <a href="#" onclick="showCategory('love')">الحب</a>
        <a href="#" onclick="showCategory('separation')">الفراق</a>
        <a href="#" onclick="showCategory('longing')">الحنين</a>
        <a href="#" onclick="showCategory('ghazal')">الغزل</a>
        <a href="#" onclick="showCategory('wisdom')">الحكمة</a>
    </div>

    <!-- Main Content Area -->
    <main class="container mx-auto px-4">
        <!-- Offset for fixed header -->
        <div class="h-[100px] sm:h-[100px] md:h-[80px]"></div>

        <!-- Home Page -->
        <section id="home-page" class="hero-section">
            <h2 class="hero-title">مرحبًا بك في موسوعة الشعر العراقي</h2>
            <p class="hero-subtitle">بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين</p>
        </section>

        <!-- Poets Page -->
        <section id="poets-page" class="py-10 sm:py-16" style="display: none;">
            <h2 class="text-4xl font-bold text-dark-heading text-center mb-10">الشعراء</h2>
            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <!-- Poet cards will be dynamically generated here -->
            </div>
        </section>

        <!-- Poet Detail Page -->
        <section id="poet-detail-page" class="poet-detail-page">
            <div class="back-button" onclick="showPoetsPage()">
                <i class="fas fa-arrow-left"></i>
                العودة إلى قائمة الشعراء
            </div>
            
            <div class="poet-detail-content">
                <h2 id="poet-detail-name"></h2>
                <p id="poet-detail-bio"></p>

                <h3 class="text-3xl font-bold text-dark-heading text-center mb-6 mt-8">قصائد الشاعر</h3>
                <div id="poem-categories" class="flex flex-wrap justify-center gap-3 mb-8">
                    <!-- Category buttons will be generated here -->
                </div>
                <div id="poems-display">
                    <!-- Poems will be displayed here -->
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="site-footer">
        <div class="container mx-auto px-4">
            <h4 class="text-3xl sm:text-4xl font-extrabold mb-4">موسوعة الشعر العراقي</h4>
            <p class="text-base leading-relaxed max-w-4xl mx-auto mb-6">
                بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي، من عمالقة الشعر إلى الأصوات الشابة.
            </p>
            <p class="text-sm mb-4">
                &copy; <span id="current-year"></span> كرار حيدر. جميع الحقوق محفوظة.
            </p>
            <div class="flex flex-col sm:flex-row justify-center items-center sm:space-x-8 space-y-4 sm:space-y-0 text-2xl mt-4">
                <a href="https://www.youtube.com/@U1QO1" target="_blank" class="hover:text-footer-link-hover transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-youtube"></i> <span>@U1QO1</span>
                </a>
                <a href="https://www.instagram.com/k9x9i" target="_blank" class="hover:text-footer-link-hover transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-instagram"></i> <span>@k9x9i</span>
                </a>
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" class="hover:text-footer-link-hover transition-colors flex items-center space-x-2 space-x-reverse">
                    <i class="fab fa-tiktok"></i> <span>@c3_i2</span>
                </a>
            </div>
        </div>
    </footer>

    <script>
        // Data for poets and poems
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
                        { title: 'عيناكِ بحرٌ من الهوى', text: 'عيناكِ بحرٌ من الهوى،\nأغرقُ فيه ولا أرتوي.\nوقلبكِ جنةٌ خضراء،\nفيها روحي تهيم وتختفي.\nيا من رسمتِ الحبَّ في عينيّ،\nيا قصةَ عمري التي لا تنتهي.\nبوجودكِ تتزينُ أيامي，\nوبقربكِ تزهرُ كلُّ أزهاري.\nأنتِ النبضُ في شراييني،\nوأنتِ الحياةُ التي أرغبُ فيها.' }
                    ],
                    wisdom: [
                        { title: 'ذو العقل يشقى في النعيم بعقله', text: 'ذو العقل يشقى في النعيم بعقله\nوأخو الجهالة في الشقاوة ينعم\nوالنفسُ راغبةٌ إذا رغّبتها\nوإذا تردّ إلى قليلٍ تقنعُ\nمن يهنْ يسهلْ الهوانُ عليه\nما لجرحٍ بميتٍ إيلامُ' }
                    ],
                    separation: [
                        { title: 'كفى بك داء أن ترى الموت شافيا', text: 'كفى بك داء أن ترى الموت شافيا\nوحسب المنايا أن يكن أمانيا\nوليس لي ذنب سوى أنني\nرأيت ما لم ترَ الأعينُ' }
                    ]
                }
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير، معالجاً قضايا الوطن والإنسان بلغة شعرية متفردة.',
                poems: {
                    love: [
                        { title: 'غريب على الخليج', text: 'الريحُ تعوي في السواحلِ،\nوأنا غريبٌ، والقلبُ ناحلُ.\nأحملُ حباً كادَ يقتلُني،\nشوقاً لعينيكِ، وليلٍ طويلِ.' }
                    ],
                    separation: [
                        { title: 'المومس العمياء', text: 'في الميناءِ، رياحٌ تهبُ،\nوصوتُ صراخٍ، لا يُجابُ.\nوالمومسُ العمياءُ تنتظرُ،\nفي ظلمةِ الليلِ، لا بابَ.' }
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
                    wisdom: [
                        { title: 'في الطريق', text: 'في الطريقِ، نتعلمُ الدروسَ،\nمن كلِّ خطوةٍ، نجدُ الحلولَ.\nلا تيأسْ، فالحياةُ رحلةٌ،\nفيها الصعابُ، وفيها الوصولُ.' }
                    ]
                }
            }
        ];

        // Update current year in footer
        document.getElementById('current-year').textContent = new Date().getFullYear();

        // Function to generate poet cards
        function generatePoetCards() {
            const poetsGrid = document.getElementById('poets-grid');
            poetsGrid.innerHTML = '';

            poetsData.forEach(poet => {
                const card = document.createElement('div');
                card.className = 'poet-grid-card';
                card.setAttribute('data-poet-id', poet.id);
                card.innerHTML = `<h3>${poet.name}</h3>`;
                card.onclick = () => showPoetDetail(poet.id);
                poetsGrid.appendChild(card);
            });
        }

        // Function to show home page
        function showHomePage() {
            document.getElementById('home-page').style.display = 'block';
            document.getElementById('poets-page').style.display = 'none';
            document.getElementById('poet-detail-page').style.display = 'none';
            closeMobileMenu();
        }

        // Function to show poets page
        function showPoetsPage() {
            document.getElementById('home-page').style.display = 'none';
            document.getElementById('poets-page').style.display = 'block';
            document.getElementById('poet-detail-page').style.display = 'none';
            generatePoetCards();
            closeMobileMenu();
        }

        // Function to show poet detail
        function showPoetDetail(poetId) {
            const poet = poetsData.find(p => p.id === poetId);
            if (!poet) return;

            document.getElementById('poet-detail-name').textContent = poet.name;
            document.getElementById('poet-detail-bio').textContent = poet.bio;

            const poemCategoriesDiv = document.getElementById('poem-categories');
            poemCategoriesDiv.innerHTML = '';
            const categories = Object.keys(poet.poems);

            categories.forEach(category => {
                const categoryButton = document.createElement('button');
                categoryButton.className = 'category-pill';
                const categoryNames = {
                    'love': 'الحب',
                    'separation': 'الفراق',
                    'longing': 'الحنين',
                    'ghazal': 'الغزل',
                    'wisdom': 'الحكمة'
                };
                categoryButton.textContent = categoryNames[category] || category;
                categoryButton.onclick = (event) => {
                    displayPoems(poet.poems[category], event);
                };
                poemCategoriesDiv.appendChild(categoryButton);
            });

            if (categories.length > 0) {
                const firstCategoryButton = poemCategoriesDiv.children[0];
                if (firstCategoryButton) {
                    firstCategoryButton.click();
                }
            }

            document.getElementById('home-page').style.display = 'none';
            document.getElementById('poets-page').style.display = 'none';
            document.getElementById('poet-detail-page').style.display = 'block';
            closeMobileMenu();
        }

        // Function to display poems
        function displayPoems(poems, event) {
            const poemsDisplayDiv = document.getElementById('poems-display');
            poemsDisplayDiv.innerHTML = '';

            document.querySelectorAll('.category-pill').forEach(button => {
                button.classList.remove('active');
            });

            if (event && event.target) {
                event.target.classList.add('active');
            }

            if (poems.length === 0) {
                poemsDisplayDiv.innerHTML = '<p class="text-center text-gray-600">لا توجد قصائد في هذا التصنيف.</p>';
                return;
            }

            poems.forEach(poem => {
                const poemCard = document.createElement('div');
                poemCard.className = 'poem-full-card';
                poemCard.innerHTML = `
                    <h4>${poem.title}</h4>
                    <p class="poem-text">${poem.text}</p>
                    <button class="copy-button" onclick="copyPoemText(this)">
                        <i class="fas fa-copy"></i> نسخ
                    </button>
                `;
                poemsDisplayDiv.appendChild(poemCard);
            });
        }

        // Function to show poems by category
        function showCategory(category) {
            const categoryNames = {
                'love': 'الحب',
                'separation': 'الفراق',
                'longing': 'الحنين',
                'ghazal': 'الغزل',
                'wisdom': 'الحكمة'
            };
            
            const poetsWithCategory = poetsData.filter(poet => poet.poems[category]);
            
            if (poetsWithCategory.length === 0) {
                alert(`لا توجد قصائد في تصنيف ${categoryNames[category]}`);
                return;
            }
            
            showPoetsPage();
            // Here you can implement filtering poets by category if needed
        }

        // Function to copy poem text
        function copyPoemText(button) {
            const poemText = button.previousElementSibling.textContent;
            navigator.clipboard.writeText(poemText).then(() => {
                const originalText = button.innerHTML;
                button.innerHTML = '<i class="fas fa-check"></i> تم النسخ!';
                setTimeout(() => {
                    button.innerHTML = originalText;
                }, 2000);
            }).catch(err => {
                console.error('Failed to copy: ', err);
            });
        }

        // Search functionality
        document.getElementById('search-input').addEventListener('input', function() {
            const searchTerm = this.value.toLowerCase();
            const filteredPoets = poetsData.filter(poet => {
                const matchesPoetName = poet.name.toLowerCase().includes(searchTerm);
                const matchesPoemTitle = Object.values(poet.poems).flat().some(poem =>
                    poem.title.toLowerCase().includes(searchTerm)
                );
                return matchesPoetName || matchesPoemTitle;
            });
            updatePoetsGrid(filteredPoets);
        });

        function updatePoetsGrid(filteredPoets) {
            const poetsGrid = document.getElementById('poets-grid');
            poetsGrid.innerHTML = '';
            if (filteredPoets.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-gray-600">لا توجد نتائج مطابقة لبحثك.</p>';
                return;
            }
            filteredPoets.forEach(poet => {
                const card = document.createElement('div');
                card.className = 'poet-grid-card';
                card.setAttribute('data-poet-id', poet.id);
                card.innerHTML = `<h3>${poet.name}</h3>`;
                card.onclick = () => showPoetDetail(poet.id);
                poetsGrid.appendChild(card);
            });
        }

        // Hamburger menu toggle
        document.getElementById('hamburger-menu-toggle').addEventListener('click', function() {
            document.getElementById('mobile-sidebar').classList.add('open');
            document.body.style.overflow = 'hidden';
        });

        function closeMobileMenu() {
            document.getElementById('mobile-sidebar').classList.remove('open');
            document.body.style.overflow = '';
        }

        // Header scroll hide/show
        let lastScrollTop = 0;
        const mainHeader = document.getElementById('main-header');

        window.addEventListener('scroll', function() {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop;

            if (scrollTop > lastScrollTop && scrollTop > 200) {
                mainHeader.classList.add('header-hidden');
            } else if (scrollTop < lastScrollTop) {
                mainHeader.classList.remove('header-hidden');
            }
            lastScrollTop = scrollTop;
        });

        // Initial load
        document.addEventListener('DOMContentLoaded', () => {
            showHomePage();
        });
    </script>
</body>
</html>

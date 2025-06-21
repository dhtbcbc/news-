<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موسوعة الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for social icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Define custom colors based on the provided image */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* A classic Arabic font */

        :root {
            --bg-dark-blue: #1A1E24; /* Dark background from image */
            --text-light-gray: #E0E0E0; /* Light text for dark background */
            --accent-orange: #F57C00; /* Orange accent from image */
            --bg-off-white: #F8F8F8; /* Off-white for search bar and hero section */
            --text-dark-gray: #333333; /* Dark gray for text on light backgrounds */
        }

        body {
            font-family: 'Amiri', 'Inter', sans-serif; /* Prioritize Arabic font */
            background-color: var(--bg-dark-blue);
            color: var(--text-light-gray);
            line-height: 1.8; /* Improve readability for Arabic text */
            overflow-x: hidden; /* Prevent horizontal scroll */
        }

        /* Custom scrollbar for better aesthetics */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-dark-blue);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--accent-orange);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-orange);
        }

        /* Hero section specific styles */
        .hero-section {
            background-color: var(--bg-off-white);
            color: var(--text-dark-gray);
            padding: 80px 0;
            text-align: center;
            border-bottom-left-radius: 50px; /* Rounded bottom-left corner */
            border-bottom-right-radius: 50px; /* Rounded bottom-right corner */
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            position: relative; /* For the background image effect */
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('https://placehold.co/1920x400/36454F/666666?text=Background'); /* Placeholder for a subtle background image */
            background-size: cover;
            background-position: center;
            opacity: 0.05; /* Very subtle */
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero-title {
            font-size: 3.5rem; /* Larger font size */
            font-weight: 700;
            color: var(--text-dark-gray);
            margin-bottom: 20px;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--text-dark-gray);
            margin-bottom: 40px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-button {
            background-color: var(--accent-orange);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(245, 124, 0, 0.4);
        }

        .hero-button:hover {
            background-color: #E66F00;
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(245, 124, 0, 0.6);
        }

        /* Search input specific styles */
        .search-input-container {
            position: relative;
            background-color: var(--bg-off-white);
            border-radius: 50px;
            padding: 8px 20px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            max-width: 600px;
            margin: 0 auto 40px; /* Center and add margin to bottom */
            display: flex;
            align-items: center;
        }

        .search-input {
            width: calc(100% - 40px); /* Adjust for icon padding */
            padding: 10px 15px;
            border: none;
            background: none;
            outline: none;
            font-size: 1.1rem;
            color: var(--text-dark-gray);
        }

        .search-icon {
            color: #999;
            font-size: 1.2rem;
        }

        /* Poet card specific styles */
        .poet-card {
            background-color: var(--bg-dark-blue);
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent; /* Default border */
        }

        .poet-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.5);
            border-color: var(--accent-orange); /* Orange border on hover */
        }

        .poet-name-display {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--text-light-gray);
            transition: color 0.3s ease;
        }

        .poet-card:hover .poet-name-display {
            color: var(--accent-orange); /* Orange text on hover */
        }

        /* Animations for interactive feel */
        .fade-in {
            opacity: 0;
            animation: fadeIn 1s ease-out forwards;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        .slide-up {
            opacity: 0;
            transform: translateY(20px);
            animation: slideUp 0.8s ease-out forwards;
        }

        @keyframes slideUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Modal styles */
        .modal {
            display: none; /* Hidden by default */
            position: fixed; /* Stay in place */
            z-index: 1000; /* Sit on top */
            left: 0;
            top: 0;
            width: 100%; /* Full width */
            height: 100%; /* Full height */
            overflow: auto; /* Enable scroll if needed */
            background-color: rgba(0,0,0,0.8); /* Darker overlay */
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal-content {
            background-color: var(--bg-dark-blue);
            color: var(--text-light-gray);
            margin: auto;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 5px 25px rgba(0,0,0,0.6);
            max-width: 900px;
            width: 95%;
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
            text-align: center;
            direction: rtl;
            border: 3px solid var(--accent-orange); /* Bold orange border for modal */
        }

        .close-button {
            color: var(--text-light-gray);
            font-size: 40px; /* Larger close button */
            font-weight: bold;
            position: absolute;
            top: 15px;
            right: 25px;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: var(--accent-orange);
            text-decoration: none;
            cursor: pointer;
        }

        .poem-title-modal {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--accent-orange);
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--text-light-gray);
        }

        .poem-text-modal {
            font-size: 1.3rem;
            white-space: pre-line;
            text-align: justify;
            margin-top: 20px;
            line-height: 2.2; /* More line height for poem readability */
            color: var(--text-light-gray);
        }

        /* Loader styles */
        .loader {
            border: 6px solid #444; /* Dark grey */
            border-top: 6px solid var(--accent-orange); /* Orange */
            border-radius: 50%;
            width: 60px;
            height: 60px;
            animation: spin 1s linear infinite;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            display: none;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Footer styles */
        footer {
            background-color: var(--bg-dark-blue);
            color: var(--text-light-gray);
            padding: 40px 0;
            text-align: center;
            border-top: 2px solid var(--accent-orange); /* Orange border at top of footer */
        }

        .footer-social-icons a {
            color: var(--text-light-gray);
            font-size: 2rem;
            margin: 0 15px;
            transition: color 0.3s ease;
        }

        .footer-social-icons a:hover {
            color: var(--accent-orange);
        }

        .footer-links a {
            color: var(--text-light-gray);
            margin: 0 10px;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--accent-orange);
        }
        /* Make important buttons more visible */
        #back-to-poets {
            background-color: var(--accent-orange); /* Orange background */
            color: white; /* White text */
            font-weight: bold;
            padding: 12px 25px;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(245, 124, 0, 0.4);
            font-size: 1.1rem;
        }

        #back-to-poets:hover {
            background-color: #E66F00;
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(245, 124, 0, 0.6);
        }

        /* Poet detail page heading */
        .poet-detail-heading {
            color: var(--accent-orange); /* Orange for heading */
            text-align: center;
            margin-bottom: 30px;
            font-size: 3rem;
            font-weight: 700;
        }
        /* Styles for the poet's bio section */
        .poet-bio-card {
            background-color: var(--bg-dark-blue);
            color: var(--text-light-gray);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 40px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.4);
            border: 2px solid var(--accent-orange); /* Orange border */
            text-align: justify;
        }

        .poet-bio-card h2 {
            font-size: 3rem;
            font-weight: bold;
            color: var(--accent-orange);
            margin-bottom: 25px;
            text-align: center;
        }

        .poet-bio-card p {
            font-size: 1.2rem;
            line-height: 2;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Poem list item styles */
        .poem-list-item {
            background-color: var(--bg-dark-blue);
            color: var(--text-light-gray);
            border-radius: 15px;
            padding: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-right: 5px solid transparent; /* Initial border */
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .poem-list-item:hover {
            background-color: #2A2E34; /* Slightly lighter dark blue on hover */
            transform: translateX(5px); /* Slight slide effect */
            border-color: var(--accent-orange); /* Orange border on hover */
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }

        .poem-list-item h4 {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--text-light-gray);
            transition: color 0.3s ease;
        }

        .poem-list-item:hover h4 {
            color: var(--accent-orange); /* Orange text on hover */
        }
    </style>
</head>
<body class="selection:bg-accent-orange/50">
    <!-- Header/Navigation Bar (Top part of the image) -->
    <header class="bg-bg-dark-blue py-6 shadow-md">
        <nav class="container mx-auto flex flex-col sm:flex-row justify-between items-center px-4">
            <div class="text-3xl font-bold text-text-light-gray mb-4 sm:mb-0">
                موسوعة الشعر العراقي
            </div>
            <ul class="flex flex-wrap justify-center gap-4 text-lg font-medium">
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">الرئيسية</a></li>
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">الشعراء</a></li>
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">شعر الحب والغزل</a></li>
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">شعر الرومانسية</a></li>
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">شعر الجرأة</a></li>
                <li><a href="#" class="text-text-light-gray hover:text-accent-orange transition-colors">أنواع أخرى</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section (Middle part of the image) -->
    <section class="hero-section">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <div class="search-input-container">
                <i class="fas fa-search search-icon ml-3"></i>
                <input type="text" id="site-search" placeholder="ابحث عن قصائد، شعراء، أو كلمات...."
                       class="search-input text-right">
            </div>

            <h1 class="hero-title fade-in" style="animation-delay: 0.2s;">مرحباً بك في <span class="text-accent-orange">موسوعة الشعر</span> العراقي</h1>
            <p class="hero-subtitle fade-in" style="animation-delay: 0.4s;">بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين</p>
            <button id="start-browsing" class="hero-button fade-in" style="animation-delay: 0.6s;">
                ابدأ التصفح
            </button>
        </div>
    </section>

    <!-- Main Container -->
    <div class="container mx-auto p-4 sm:p-6 lg:p-8">
        <!-- Poets Page (Default view) -->
        <section id="poets-page" class="py-10">
            <h2 class="text-4xl font-extrabold text-center mb-10 text-accent-orange drop-shadow-lg fade-in" style="animation-delay: 0.8s;">الشعراء البارزون</h2>

            <div class="flex flex-col sm:flex-row items-center justify-center mb-12 gap-4 fade-in" style="animation-delay: 1s;">
                <input type="text" id="poet-search" placeholder="ابحث عن شاعر..."
                       class="p-3 border-2 border-accent-orange rounded-full focus:outline-none focus:ring-2 focus:ring-accent-orange w-full sm:w-80 text-lg text-right shadow-md bg-bg-dark-blue text-text-light-gray">
                <button id="search-button"
                        class="bg-accent-orange hover:bg-orange-700 text-white font-bold py-3 px-6 rounded-full transition-all duration-300 transform hover:scale-105 shadow-lg">
                    بحث
                </button>
            </div>

            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
                <!-- Poet cards will be rendered here by JavaScript -->
            </div>
        </section>

        <!-- Poet Detail Page (Hidden by default) -->
        <section id="poet-detail-page" class="py-10 hidden">
            <button id="back-to-poets"
                    class="mb-8 bg-accent-orange hover:bg-orange-700 text-white font-bold py-3 px-6 rounded-full transition-all duration-300 transform hover:scale-105 shadow-lg">
                العودة إلى الشعراء
            </button>

            <div class="poet-bio-card">
                <h2 id="poet-detail-name" class="fade-in"></h2>
                <p id="poet-detail-bio" class="fade-in" style="animation-delay: 0.2s;"></p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-accent-orange fade-in" style="animation-delay: 0.4s;">قصائد الشاعر</h3>
            <div class="flex items-center justify-center mb-8 fade-in" style="animation-delay: 0.6s;">
                <input type="text" id="poem-search" placeholder="ابحث عن قصيدة..."
                       class="p-3 border-2 border-accent-orange rounded-full focus:outline-none focus:ring-2 focus:ring-accent-orange w-full sm:w-96 text-lg text-right shadow-md bg-bg-dark-blue text-text-light-gray">
            </div>

            <ul id="poems-list" class="space-y-4">
                <!-- Poem titles will be rendered here by JavaScript -->
            </ul>
        </section>
    </div>

    <!-- Modal for displaying full poem text -->
    <div id="poem-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" id="close-poem-modal">&times;</span>
            <div class="loader" id="modal-loader"></div>
            <h3 id="modal-poem-title" class="poem-title-modal"></h3>
            <p id="modal-poem-text" class="poem-text-modal"></p>
        </div>
    </div>

    <!-- Footer (Bottom part of the image) -->
    <footer class="mt-12">
        <div class="container mx-auto px-4 py-8">
            <div class="mb-6">
                <h3 class="text-3xl font-bold mb-4 text-accent-orange">موسوعة الشعر العراقي</h3>
                <p class="text-lg leading-relaxed max-w-2xl mx-auto">
                    بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي من عمالقة الشعر إلى الأصوات الشابة. نسعى لإثراء الساحة الأدبية وتقديم أرشيف متكامل يعكس جمال وعمق الكلمة العراقية.
                </p>
            </div>

            <p class="text-md mb-6">&copy; 2025 كرار حيدر. جميع الحقوق محفوظة.</p>

            <div class="footer-social-icons mb-6">
                <a href="https://www.youtube.com/@U1QO1" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
                <a href="https://www.instagram.com/k9x9i" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://www.tiktok.com/@c3_i2" target="_blank" aria-label="TikTok"><i class="fab fa-tiktok"></i></a>
            </div>

            <div class="footer-links text-sm">
                <a href="#">سياسة الخصوصية</a> |
                <a href="#">شروط الاستخدام</a> |
                <a href="#">خريطة الموقع</a>
            </div>
        </div>
    </footer>

    <script>
        // Placeholder data for poets and poems
        const poetsData = [
            {
                id: 'al_mutanabbi',
                name: 'أبو الطيب المتنبي',
                bio: 'هو أحمد بن الحسين الجعفي الكندي الكوفي أبو الطيب المتنبي. أحد أعظم شعراء العرب، ولد بالكوفة سنة 303 هـ وتوفي سنة 354 هـ. اشتهر بقوة لغته وفصاحته، وحكمته في شعره الذي تناول المدح والهجاء والرثاء والفخر والحكمة.',
                poems: [
                    { title: 'أنا الذي نظر الأعمى إلى أدبي' },
                    { title: 'على قدر أهل العزم تأتي العزائم' },
                    { title: 'وإذا كانت النفوس كباراً' }
                ]
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير.',
                poems: [
                    { title: 'أنشودة المطر' },
                    { title: 'مدينة بلا مطر' }
                ]
            },
            {
                id: 'nazik_al_malaika',
                name: 'نازك الملائكة',
                bio: 'شاعرة عراقية وناقدة، ولدت في بغداد عام 1923 وتوفيت في القاهرة عام 2007. تُعد من أهم رواد الشعر الحر في الأدب العربي، إلى جانب بدر شاكر السياب وعبد الوهاب البياتي. تميزت قصائدها بجمال اللغة وعمق المعنى والفلسفة.',
                poems: [
                    { title: 'الكوليرا' },
                    { title: 'عاشقة الليل' }
                ]
            },
            {
                id: 'abd_al_wahhab',
                name: 'عبد الوهاب البياتي',
                bio: 'شاعر عراقي بارز من رواد حركة الشعر الحر، ولد في بغداد عام 1926 وتوفي في دمشق عام 1999. عرف بشعره الغزير والمتنوع الذي يجمع بين الواقعية والرمزية، ويعكس هموم الإنسان العربي وقضاياه الاجتماعية والسياسية.',
                poems: [
                    { title: 'سوق القرية' },
                    { title: 'النار والكلمات' }
                ]
            },
            {
                id: 'jamil_sidqi',
                name: 'جميل صدقي الزهاوي',
                bio: 'شاعر وفيلسوف عراقي، ولد في بغداد عام 1863 وتوفي فيها عام 1936. يعتبر من أبرز شعراء العراق في العصر الحديث، واشتهر بشعره الذي يدعو إلى الإصلاح الاجتماعي والنهضة والحرية، وكان من دعاة تحرير المرأة.',
                poems: [
                    { title: 'الخمر' },
                    { title: 'الزهاوي عن المرأة' }
                ]
            },
            {
                id: 'ma_ruf_al_rusafi',
                name: 'معروف الرصافي',
                bio: 'شاعر عراقي كبير، ولد في بغداد عام 1875 وتوفي فيها عام 1945. يعد من رواد الشعر الحديث في العراق، وعرف بشعره الوطني والاجتماعي الذي يلامس قضايا الفقر والجهل والظلم، وكان له دور كبير في الصحافة العراقية.',
                poems: [
                    { title: 'الأرملة المرضعة' },
                    { title: 'في دار الأيتام' }
                ]
            }
        ];

        // Get DOM elements
        const poetsPage = document.getElementById('poets-page');
        const poetDetailPage = document.getElementById('poet-detail-page');
        const poetsGrid = document.getElementById('poets-grid');
        const poetSearchInput = document.getElementById('poet-search');
        const searchButton = document.getElementById('search-button');
        const startBrowsingButton = document.getElementById('start-browsing');
        const backToPoetsButton = document.getElementById('back-to-poets');

        const poetDetailName = document.getElementById('poet-detail-name');
        const poetDetailBio = document.getElementById('poet-detail-bio');
        const poemsList = document.getElementById('poems-list');
        const poemSearchInput = document.getElementById('poem-search');

        const poemModal = document.getElementById('poem-modal');
        const closePoemModalButton = document.getElementById('close-poem-modal');
        const modalPoemTitle = document.getElementById('modal-poem-title');
        const modalPoemText = document.getElementById('modal-poem-text');
        const modalLoader = document.getElementById('modal-loader');

        let currentPoetId = null; // To keep track of the currently viewed poet

        // Function to render poet cards with fade-in animation
        function renderPoets(poetsToRender) {
            poetsGrid.innerHTML = ''; // Clear previous poets
            if (poetsToRender.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-xl text-red-400 mt-8">لا توجد نتائج مطابقة.</p>';
                return;
            }
            poetsToRender.forEach((poet, index) => {
                const poetCard = document.createElement('div');
                poetCard.classList.add('poet-card', 'slide-up');
                poetCard.style.animationDelay = `${0.1 * index}s`; // Staggered animation
                poetCard.innerHTML = `
                    <h3 class="poet-name-display">${poet.name}</h3>
                `;
                poetCard.addEventListener('click', () => displayPoetDetail(poet.id));
                poetsGrid.appendChild(poetCard);
            });
        }

        // Function to display poet detail page with animations
        async function displayPoetDetail(poetId) {
            const poet = poetsData.find(p => p.id === poetId);
            if (!poet) {
                console.error('Poet not found:', poetId);
                return;
            }

            currentPoetId = poetId; // Set current poet

            poetDetailName.textContent = poet.name;
            poetDetailBio.textContent = poet.bio;

            // Apply fade-in to elements in detail page
            poetDetailName.classList.add('fade-in');
            poetDetailBio.classList.add('fade-in');
            document.querySelector('#poet-detail-page h3').classList.add('fade-in');
            document.querySelector('#poet-detail-page .flex.items-center').classList.add('fade-in');

            renderPoemsForPoet(poet.poems);

            poetsPage.classList.add('hidden');
            poetDetailPage.classList.remove('hidden');
            window.scrollTo(0, 0); // Scroll to top of the page
        }

        // Function to render poems for the current poet with slide-up animation
        function renderPoemsForPoet(poemsToRender) {
            poemsList.innerHTML = ''; // Clear previous poems
            if (poemsToRender.length === 0) {
                poemsList.innerHTML = '<p class="text-center text-lg text-text-light-gray mt-8">لا توجد قصائد لهذا الشاعر حتى الآن.</p>';
                return;
            }
            poemsToRender.forEach((poem, index) => {
                const listItem = document.createElement('li');
                listItem.classList.add('poem-list-item', 'slide-up');
                listItem.style.animationDelay = `${0.1 * index}s`; // Staggered animation
                listItem.innerHTML = `
                    <h4 class="text-xl font-semibold">${poem.title}</h4>
                `;
                listItem.addEventListener('click', () => showPoemModal(poem));
                poemsList.appendChild(listItem);
            });
        }

        // Function to show the poem modal and fetch poem content
        async function showPoemModal(poem) {
            modalPoemTitle.textContent = poem.title;
            modalPoemText.textContent = ''; // Clear previous text
            modalLoader.style.display = 'block'; // Show loader
            poemModal.style.display = 'flex'; // Show modal

            // Construct prompt for LLM
            const poetName = poetsData.find(p => p.id === currentPoetId)?.name || "شاعر";
            const prompt = `اكتب القصيدة كاملة بعنوان "${poem.title}" للشاعر ${poetName}. إذا لم تكن القصيدة معروفة أو متوفرة، قم بتوليد قصيدة أصلية وملهمة بهذا العنوان وبأسلوب الشاعر المعروف بـ "${poetName}". اجعل القصيدة تحتوي على معاني عميقة وجمالية، ومناسبة لطبيعة الشعر العراقي.`;

            let chatHistory = [];
            chatHistory.push({ role: "user", parts: [{ text: prompt }] });
            const payload = { contents: chatHistory };
            const apiKey = ""; // Canvas will provide this
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                const result = await response.json();
                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const generatedText = result.candidates[0].content.parts[0].text;
                    modalPoemText.textContent = generatedText;
                } else {
                    modalPoemText.textContent = 'تعذر تحميل القصيدة. قد لا تكون متوفرة أو حدث خطأ في التوليد.';
                    console.error('API response error:', result);
                }
            } catch (error) {
                modalPoemText.textContent = 'حدث خطأ أثناء تحميل القصيدة. يرجى التحقق من اتصالك بالإنترنت.';
                console.error('Fetch error:', error);
            } finally {
                modalLoader.style.display = 'none'; // Hide loader
            }
        }

        // Function to hide the poem modal
        function hidePoemModal() {
            poemModal.style.display = 'none';
        }

        // Event Listeners
        window.onload = () => {
            renderPoets(poetsData); // Render all poets on load
        };

        poetSearchInput.addEventListener('input', (event) => {
            const searchTerm = event.target.value.toLowerCase();
            const filteredPoets = poetsData.filter(poet =>
                poet.name.toLowerCase().includes(searchTerm)
            );
            renderPoets(filteredPoets);
        });

        searchButton.addEventListener('click', () => {
            const searchTerm = poetSearchInput.value.toLowerCase();
            const filteredPoets = poetsData.filter(poet =>
                poet.name.toLowerCase().includes(searchTerm)
            );
            renderPoets(filteredPoets);
        });

        // Event listener for the "ابدأ التصفح" button
        startBrowsingButton.addEventListener('click', () => {
            poetsPage.scrollIntoView({ behavior: 'smooth' }); // Smooth scroll to poets section
        });


        poemSearchInput.addEventListener('input', (event) => {
            const searchTerm = event.target.value.toLowerCase();
            const currentPoet = poetsData.find(p => p.id === currentPoetId);
            if (currentPoet) {
                const filteredPoems = currentPoet.poems.filter(poem =>
                    poem.title.toLowerCase().includes(searchTerm)
                );
                renderPoemsForPoet(filteredPoems);
            }
        });

        backToPoetsButton.addEventListener('click', () => {
            poetDetailPage.classList.add('hidden');
            poetsPage.classList.remove('hidden');
            poetSearchInput.value = ''; // Clear search bar
            renderPoets(poetsData); // Re-render all poets
            poemSearchInput.value = ''; // Clear poem search bar
            window.scrollTo(0, 0); // Scroll to top of the page
        });

        closePoemModalButton.addEventListener('click', hidePoemModal);

        // Close modal when clicking outside of it
        window.addEventListener('click', (event) => {
            if (event.target === poemModal) {
                hidePoemModal();
            }
        });

        // Close modal with Escape key
        document.addEventListener('keydown', (event) => {
            if (event.key === 'Escape' && poemModal.style.display === 'flex') {
                hidePoemModal();
            }
        });
    </script>
</body>
</html>

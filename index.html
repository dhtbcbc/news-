<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ديوان الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for Hamburger Icon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Define custom colors and font based on the suggestions and image */
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap'); /* A clear, bold Arabic font */
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* Secondary classic Arabic font */

        :root {
            --dark-bg: #222831; /* Dark background from image analysis */
            --light-bg: #FAF8F4; /* Suggested warm beige for contrasts */
            --text-dark: #EEEEEE; /* Light text on dark background */
            --text-accent: #FFD369; /* Golden yellow accent */
            --button-primary: #00ADB5; /* Turquoise blue for main buttons */
            --button-hover: #5eead4; /* Lighter turquoise for hover */
        }

        body {
            font-family: 'Cairo', 'Amiri', sans-serif; /* Prioritize Cairo for boldness */
            background-color: var(--dark-bg); /* Apply dark background to entire body */
            color: var(--text-dark);
            line-height: 1.8; /* Improve readability for Arabic text */
            scroll-behavior: smooth; /* Smooth scrolling for animations */
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--dark-bg);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--button-primary);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--text-accent);
        }

        /* --- Header Styles --- */
        .fixed-header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 50;
            background-color: var(--dark-bg);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease-in-out;
        }

        .header-hidden {
            transform: translateY(-100%);
        }

        /* --- Hamburger Menu Styles --- */
        .sidebar {
            height: 100%;
            width: 0; /* Hidden by default */
            position: fixed;
            z-index: 100;
            top: 0;
            right: 0; /* From right for RTL */
            background-color: var(--dark-bg);
            overflow-x: hidden;
            transition: 0.5s;
            padding-top: 60px;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.5);
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .sidebar a {
            padding: 15px 8px 15px 32px;
            text-decoration: none;
            font-size: 25px;
            color: var(--text-dark);
            display: block;
            transition: 0.3s;
            width: 100%;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .sidebar a:hover {
            color: var(--text-accent);
            background-color: rgba(255, 255, 255, 0.1);
        }

        .sidebar .closebtn {
            position: absolute;
            top: 0;
            left: 25px; /* Adjust for RTL */
            font-size: 36px;
            margin-left: 50px;
        }

        /* --- Poet Card Animations --- */
        .poet-card-hidden {
            opacity: 0;
            transform: translateX(-50px); /* Appear from left */
        }

        .poet-card-visible {
            opacity: 1;
            transform: translateX(0);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        /* --- Modal Styles --- */
        .modal {
            display: none; /* Hidden by default */
            position: fixed; /* Stay in place */
            z-index: 1000; /* Sit on top */
            left: 0;
            top: 0;
            width: 100%; /* Full width */
            height: 100%; /* Full height */
            overflow: auto; /* Enable scroll if needed */
            background-color: rgba(0,0,0,0.7); /* Black w/ opacity */
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal-content {
            background-color: var(--light-bg);
            margin: auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            max-width: 800px;
            width: 90%;
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
            text-align: center;
            direction: rtl;
        }

        .close-button {
            color: var(--dark-bg);
            font-size: 36px;
            font-weight: bold;
            position: absolute;
            top: 10px;
            left: 20px; /* Adjust for RTL */
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: var(--button-primary);
            text-decoration: none;
            cursor: pointer;
        }

        .poem-title-modal {
            font-size: 2rem;
            font-weight: bold;
            color: var(--button-primary);
            margin-bottom: 20px;
            border-bottom: 2px solid var(--text-accent);
            padding-bottom: 10px;
        }

        .poem-text-modal {
            font-family: 'Amiri', serif; /* Use a classic font for poem text */
            font-size: 1.2rem;
            white-space: pre-line;
            text-align: justify;
            margin-top: 20px;
            color: var(--dark-bg); /* Dark text on light modal background */
        }

        @media (max-width: 768px) {
            .poem-text-modal {
                font-size: 1rem;
            }
        }

        /* Loading indicator styles */
        .loader {
            border: 6px solid #f3f3f3; /* Light grey */
            border-top: 6px solid var(--button-primary); /* Blue */
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            display: none; /* Hidden by default */
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="selection:bg-text-accent/50">

    <!-- Hamburger Menu Sidebar -->
    <div id="mySidebar" class="sidebar">
        <a href="javascript:void(0)" class="closebtn" onclick="closeNav()">&times;</a>
        <a href="#" onclick="showPoetsPage()">الرئيسية</a>
        <a href="#" onclick="showPoetsPage()">الشعراء</a>
        <a href="#" onclick="showCategory('love')">شعر الحب</a>
        <a href="#" onclick="showCategory('sadness')">شعر الحزن</a>
        <a href="#" onclick="showCategory('longing')">شعر الاشتياق</a>
        <a href="#" onclick="showCategory('joy')">شعر الفرح</a>
        <a href="#" onclick="showCategory('wisdom')">شعر الحكمة</a>
        <a href="#">أنواع أخرى</a>
    </div>

    <!-- Fixed Header -->
    <header id="main-header" class="fixed-header flex justify-between items-center px-4 py-3 sm:px-6 lg:px-8">
        <div class="flex items-center gap-4">
            <h1 class="text-3xl sm:text-4xl font-extrabold text-text-accent whitespace-nowrap">موسوعة الشعر العراقي</h1>
            <div class="relative w-full sm:w-64">
                <input type="text" id="main-search" placeholder="ابحث عن قصائد، شعراء..."
                       class="p-2 pl-10 border-2 border-button-primary rounded-full focus:outline-none focus:ring-2 focus:ring-text-accent w-full text-lg text-right bg-dark-bg text-text-dark placeholder-gray-400">
                <i class="fa fa-search absolute right-3 top-1/2 -translate-y-1/2 text-gray-400"></i>
            </div>
        </div>
        <button class="text-text-dark text-3xl sm:text-4xl p-2 rounded-lg hover:bg-gray-700 transition-colors" onclick="openNav()">
            <i class="fas fa-bars"></i>
        </button>
    </header>
    <div class="h-[76px] sm:h-[84px]"></div> <!-- Placeholder for fixed header height -->

    <!-- Main Content Container -->
    <div class="container mx-auto px-4 sm:px-6 lg:px-8 pb-10">

        <!-- Poets Page (Default view) -->
        <section id="poets-page" class="py-10">
            <!-- Welcome Section -->
            <div class="bg-light-bg rounded-2xl shadow-xl p-6 sm:p-10 mb-12 text-center border-b-4 border-button-primary">
                <h2 class="text-4xl sm:text-5xl font-extrabold mb-4 text-dark-bg leading-tight">مرحباً بك في موسوعة الشعر العراقي</h2>
                <p class="text-xl sm:text-2xl text-dark-bg leading-relaxed max-w-3xl mx-auto">بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين</p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-text-accent">الشعراء البارزون</h3>
            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
                <!-- Poet cards will be rendered here by JavaScript -->
            </div>
        </section>

        <!-- Poet Detail Page (Hidden by default) -->
        <section id="poet-detail-page" class="py-10 hidden">
            <button id="back-to-poets"
                    class="mb-8 bg-text-accent hover:bg-button-primary text-dark-bg font-bold py-2 px-5 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                العودة إلى الشعراء
            </button>

            <div class="bg-light-bg rounded-2xl shadow-xl p-8 mb-10 text-center border-b-4 border-button-primary">
                <img id="poet-detail-image" src="" alt="صورة الشاعر" class="w-40 h-40 rounded-full mx-auto mb-6 object-cover border-4 border-text-accent shadow-lg">
                <h2 id="poet-detail-name" class="text-4xl font-extrabold mb-4 text-dark-bg"></h2>
                <p id="poet-detail-bio" class="text-lg leading-relaxed text-dark-bg text-justify max-w-4xl mx-auto"></p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-text-accent">قصائد الشاعر</h3>
            <div id="poem-categories" class="flex flex-wrap justify-center gap-3 mb-8">
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="general">عامة</button>
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="love">حب</button>
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="sadness">حزن</button>
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="longing">اشتياق</button>
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="joy">فرح</button>
                <button class="category-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="wisdom">حكمة</button>
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

    <!-- Footer -->
    <footer class="bg-dark-bg py-6 text-center shadow-inner mt-10">
        <p class="text-text-dark text-sm">&copy; <span id="current-year"></span> كرار حيدر. جميع الحقوق محفوظة.</p>
    </footer>

    <script>
        // Data for poets and poems
        const poetsData = [
            {
                id: 'al_mutanabbi',
                name: 'أبو الطيب المتنبي',
                image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Al_Mutanabbi.jpg/300px-Al_Mutanabbi.jpg',
                bio: 'هو أحمد بن الحسين الجعفي الكندي الكوفي أبو الطيب المتنبي. أحد أعظم شعراء العرب، ولد بالكوفة سنة 303 هـ وتوفي سنة 354 هـ. اشتهر بقوة لغته وفصاحته، وحكمته في شعره الذي تناول المدح والهجاء والرثاء والفخر والحكمة. يُعتبر شعره قمة الإبداع الأدبي العربي، وقد حفظ منه الكثير وصار مضرب الأمثال.',
                poems: {
                    general: [
                        { title: 'أنا الذي نظر الأعمى إلى أدبي' },
                        { title: 'على قدر أهل العزم تأتي العزائم' },
                        { title: 'وإذا كانت النفوس كباراً' }
                    ],
                    love: [
                        { title: 'أحبك لو كان حبي داءً' },
                        { title: 'فبتّ كأنني أسقى رضاباً' }
                    ],
                    sadness: [
                        { title: 'كفى بك داء أن ترى الموت شافيا' },
                        { title: 'ما كل ما يتمنى المرء يدركه' }
                    ],
                    longing: [
                        { title: 'إذا ترحلت عن قوم وقد قدروا' },
                        { title: 'وحشتك يا سماء الشوق روحي' }
                    ],
                    joy: [
                        { title: 'عيد بأي حال عدت يا عيد' },
                        { title: 'الخيل والليل والبيداء تعرفني' }
                    ],
                    wisdom: [
                        { title: 'ذو العقل يشقى في النعيم بعقله' },
                        { title: 'إذا أنت أكرمت الكريم ملكته' }
                    ]
                }
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                image: 'https://upload.wikimedia.org/wikipedia/ar/thumb/8/87/Bader_Shaker_Al-Sayab.jpg/250px-Bader_Shaker_Al-Sayab.jpg',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير، معالجاً قضايا الوطن والإنسان بلغة شعرية متفردة.',
                poems: {
                    general: [
                        { title: 'أنشودة المطر' },
                        { title: 'مدينة بلا مطر' }
                    ],
                    love: [
                        { title: 'غريب على الخليج' },
                        { title: 'كانت لدي وردة' }
                    ],
                    sadness: [
                        { title: 'المومس العمياء' },
                        { title: 'حفار القبور' }
                    ],
                    longing: [
                        { title: 'رسالة إلى جيكور' },
                        { title: 'لأني غريب' }
                    ],
                    joy: [
                        { title: 'أزهار و أساطير' },
                        { title: 'فجر' }
                    ],
                    wisdom: [
                        { title: 'أقوال من زمن قديم' },
                        { title: 'الشعر هو الحياة' }
                    ]
                }
            },
            {
                id: 'nazik_al_malaika',
                name: 'نازك الملائكة',
                image: 'https://upload.wikimedia.org/wikipedia/ar/thumb/9/91/Nzk_Almlayk.jpg/220px-Nzk_Almlayk.jpg',
                bio: 'شاعرة عراقية وناقدة، ولدت في بغداد عام 1923 وتوفيت في القاهرة عام 2007. تُعد من أهم رواد الشعر الحر في الأدب العربي، إلى جانب بدر شاكر السياب وعبد الوهاب البياتي. تميزت قصائدها بجمال اللغة وعمق المعنى والفلسفة، وتناولت مواضيع الحرية والمرأة والحياة والموت.',
                poems: {
                    general: [
                        { title: 'الكوليرا' },
                        { title: 'عاشقة الليل' }
                    ],
                    love: [
                        { title: 'أنا والليل' },
                        { title: 'حبيبي يا ساكن الروح' }
                    ],
                    sadness: [
                        { title: 'شجرة القمر' },
                        { title: 'قنص المجهول' }
                    ],
                    longing: [
                        { title: 'وحدة' },
                        { title: 'المساء في القرية' }
                    ],
                    joy: [
                        { title: 'يوميات' },
                        { title: 'فرحة الألوان' }
                    ],
                    wisdom: [
                        { title: 'في الطريق' },
                        { title: 'الشعر فن الحياة' }
                    ]
                }
            },
            {
                id: 'abd_al_wahhab',
                name: 'عبد الوهاب البياتي',
                image: 'https://upload.wikimedia.org/wikipedia/ar/thumb/8/87/Abd_al-Wahhab_al-Bayati.jpg/220px-Abd_al-Wahhab_al-Bayati.jpg',
                bio: 'شاعر عراقي بارز من رواد حركة الشعر الحر، ولد في بغداد عام 1926 وتوفي في دمشق عام 1999. عرف بشعره الغزير والمتنوع الذي يجمع بين الواقعية والرمزية، ويعكس هموم الإنسان العربي وقضاياه الاجتماعية والسياسية، ويُعتبر صوته الشعري معبراً عن جيل بأكمله.',
                poems: {
                    general: [
                        { title: 'سوق القرية' },
                        { title: 'النار والكلمات' }
                    ],
                    love: [
                        { title: 'عينيها' },
                        { title: 'ألف ليلة وليلة' }
                    ],
                    sadness: [
                        { title: 'الذي يأتي ولا يأتي' },
                        { title: 'الموت في بغداد' }
                    ],
                    longing: [
                        { title: 'رحلة في أعماق الذاكرة' },
                        { title: 'نداء الروح' }
                    ],
                    joy: [
                        { title: 'إلى حبيبته' },
                        { title: 'فرحة العود' }
                    ],
                    wisdom: [
                        { title: 'كتاب الفقر والثورة' },
                        { title: 'الحكمة الضائعة' }
                    ]
                }
            },
            {
                id: 'jamil_sidqi',
                name: 'جميل صدقي الزهاوي',
                image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Jamil_Sidqi_al-Zahawi.jpg/220px-Jamil_Sidqi_al-Zahawi.jpg',
                bio: 'شاعر وفيلسوف عراقي، ولد في بغداد عام 1863 وتوفي فيها عام 1936. يعتبر من أبرز شعراء العراق في العصر الحديث، واشتهر بشعره الذي يدعو إلى الإصلاح الاجتماعي والنهضة والحرية، وكان من دعاة تحرير المرأة. شعره اتسم بالجرأة الفكرية والأسلوب البليغ.',
                poems: {
                    general: [
                        { title: 'الخمر' },
                        { title: 'الزهاوي عن المرأة' }
                    ],
                    love: [
                        { title: 'غرامي المستحيل' },
                        { title: 'إلى حبيبتي' }
                    ],
                    sadness: [
                        { title: 'مرثية بغداد' },
                        { title: 'شكوى الزمن' }
                    ],
                    longing: [
                        { title: 'الشوق إلى الماضي' },
                        { title: 'أحن إليك' }
                    ],
                    joy: [
                        { title: 'بشائر العيد' },
                        { title: 'نشوة الحياة' }
                    ],
                    wisdom: [
                        { title: 'درس الحياة' },
                        { title: 'من أقوال الحكماء' }
                    ]
                }
            },
            {
                id: 'ma_ruf_al_rusafi',
                name: 'معروف الرصافي',
                image: 'https://upload.wikimedia.org/wikipedia/ar/thumb/5/52/Al_Rusafi.jpg/220px-Al_Rusafi.jpg',
                bio: 'شاعر عراقي كبير، ولد في بغداد عام 1875 وتوفي فيها عام 1945. يعد من رواد الشعر الحديث في العراق، وعرف بشعره الوطني والاجتماعي الذي يلامس قضايا الفقر والجهل والظلم، وكان له دور كبير في الصحافة العراقية، داعياً للعدالة والتعليم ومناهضة الاستبداد.',
                poems: {
                    general: [
                        { title: 'الأرملة المرضعة' },
                        { title: 'في دار الأيتام' }
                    ],
                    love: [
                        { title: 'أنت الحبيب' },
                        { title: 'همسة حب' }
                    ],
                    sadness: [
                        { title: 'وداع بغداد' },
                        { title: 'شكوى فلاح' }
                    ],
                    longing: [
                        { title: 'حنين إلى الوطن' },
                        { title: 'يا بغداد لا تشجعي' }
                    ],
                    joy: [
                        { title: 'تحية العيد' },
                        { title: 'بشائر النصر' }
                    ],
                    wisdom: [
                        { title: 'العلم والأخلاق' },
                        { title: 'الحياة دروس' }
                    ]
                }
            },
            {
                id: 'mohammad_mahdi_al_jawahiri',
                name: 'محمد مهدي الجواهري',
                image: 'https://upload.wikimedia.org/wikipedia/ar/thumb/a/a2/%D9%85%D8%AD%D9%85%D8%AF_%D9%85%D9%87%D8%AF%D9%8A_%D8%A7%D9%84%D8%AC%D9%88%D8%A7%D9%87%D8%B1%D9%8A.jpg/220px-%D9%85%D8%AD%D9%85%D8%AF_%D9%85%D9%87%D8%AF%D9%8A_%D8%A7%D9%84%D8%AC%D9%88%D8%A7%D9%87%D8%B1%D9%8A.jpg',
                bio: 'شاعر عربي عراقي يُلقب بـ "نهر العراق الثالث" و "شاعر العرب الأكبر". ولد في النجف عام 1899 وتوفي في دمشق عام 1997. يعتبر من أبرز شعراء العصر الحديث، وامتاز بغزارة إنتاجه وقوة أسلوبه وشاعريته الفذة التي غطت مختلف الأغراض الشعرية من وطنية وقومية ووجدانية.',
                poems: {
                    general: [
                        { title: 'يا دجلة الخير' },
                        { title: 'إلى أمي' }
                    ],
                    love: [
                        { title: 'أتتني ذات يوم' },
                        { title: 'حديث القلب' }
                    ],
                    sadness: [
                        { title: 'ليلة وداع' },
                        { title: 'شكوى من الغربة' }
                    ],
                    longing: [
                        { title: 'أيها الوطن' },
                        { title: 'الشوق إلى بغداد' }
                    ],
                    joy: [
                        { title: 'ذكرى ثورة' },
                        { title: 'فرحة الأمل' }
                    ],
                    wisdom: [
                        { title: 'كن في الحياة' },
                        { title: 'فلسفة الحياة' }
                    ]
                }
            },
            {
                id: 'abdul_ghani_al_raoui',
                name: 'عبد الغني الراوي',
                image: 'https://placehold.co/150x150/00ADB5/ffffff?text=الراوي',
                bio: 'شاعر عراقي معاصر، يُعرف بأسلوبه المميز الذي يجمع بين الأصالة والمعاصرة. ولد في العراق وله العديد من الدواوين الشعرية التي تتناول مواضيع متنوعة مثل الحب والوطن وقضايا الإنسان المعاصر، ويُعتبر صوته من الأصوات الشعرية الجديدة والمؤثرة في الساحة الأدبية العراقية.',
                poems: {
                    general: [
                        { title: 'بغداد الحبيبة' },
                        { title: 'نهر الحياة' }
                    ],
                    love: [
                        { title: 'عيناكِ سرُّ وجودي' },
                        { title: 'قصيدة حب أبدية' }
                    ],
                    sadness: [
                        { title: 'وجع الروح' },
                        { title: 'دموع الفراق' }
                    ],
                    longing: [
                        { title: 'شوق إلى الأمس' },
                        { title: 'حنين الوطن' }
                    ],
                    joy: [
                        { title: 'لحظة أمل' },
                        { title: 'ابتسامة الحياة' }
                    ],
                    wisdom: [
                        { title: 'دروس الأيام' },
                        { title: 'حكمة الزمن' }
                    ]
                }
            }
        ];

        // Get DOM elements
        const poetsPage = document.getElementById('poets-page');
        const poetDetailPage = document.getElementById('poet-detail-page');
        const poetsGrid = document.getElementById('poets-grid');
        const mainSearchInput = document.getElementById('main-search');
        const backToPoetsButton = document.getElementById('back-to-poets');

        const poetDetailImage = document.getElementById('poet-detail-image');
        const poetDetailName = document.getElementById('poet-detail-name');
        const poetDetailBio = document.getElementById('poet-detail-bio');
        const poemsList = document.getElementById('poems-list');
        const poemCategoriesContainer = document.getElementById('poem-categories');

        const poemModal = document.getElementById('poem-modal');
        const closePoemModalButton = document.getElementById('close-poem-modal');
        const modalPoemTitle = document.getElementById('modal-poem-title');
        const modalPoemText = document.getElementById('modal-poem-text');
        const modalLoader = document.getElementById('modal-loader');

        const mySidebar = document.getElementById("mySidebar");
        const mainHeader = document.getElementById("main-header");
        const currentYearSpan = document.getElementById("current-year");

        let currentPoetId = null; // To keep track of the currently viewed poet
        let currentPoemCategory = 'general'; // Default category for poems

        // --- Hamburger Menu Logic ---
        function openNav() {
            mySidebar.style.width = "250px"; /* Sidebar width */
        }

        function closeNav() {
            mySidebar.style.width = "0";
        }

        let lastScrollTop = 0;
        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            if (scrollTop > lastScrollTop) {
                // Scrolling down
                mainHeader.classList.add('header-hidden');
                closeNav(); // Close sidebar if scrolling down
            } else {
                // Scrolling up
                mainHeader.classList.remove('header-hidden');
            }
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; // For Mobile or negative scrolling
        });

        // --- Page Navigation Functions ---
        function showPoetsPage() {
            poetDetailPage.classList.add('hidden');
            poetsPage.classList.remove('hidden');
            mainSearchInput.value = ''; // Clear main search bar
            renderPoets(poetsData); // Re-render all poets
            closeNav(); // Close sidebar
            window.scrollTo(0, 0); // Scroll to top
        }

        function showCategory(category) {
            closeNav(); // Close sidebar
            // This function would ideally filter poets based on some metadata,
            // or perhaps navigate to a general category page listing poems from all poets in that category.
            // For this implementation, it will just log the category and return to poets page for simplicity.
            // In a real app, you'd build a new view for categories.
            alert(`سيتم عرض قصائد من فئة: ${category === 'love' ? 'الحب' : category === 'sadness' ? 'الحزن' : category === 'longing' ? 'الاشتياق' : category === 'joy' ? 'الفرح' : category === 'wisdom' ? 'الحكمة' : 'عامة'}. هذا قسم قيد الإنشاء!`);
            showPoetsPage(); // Go back to poets page for now
        }

        // --- Poet Card Rendering and Animations ---
        function renderPoets(poetsToRender) {
            poetsGrid.innerHTML = ''; // Clear previous poets
            if (poetsToRender.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-xl text-text-accent">لا توجد نتائج مطابقة.</p>';
                return;
            }
            poetsToRender.forEach((poet, index) => {
                const poetCard = document.createElement('div');
                poetCard.classList.add('bg-light-bg', 'rounded-2xl', 'shadow-lg', 'p-6', 'text-center', 'transform', 'transition-transform', 'duration-300', 'hover:scale-105', 'hover:shadow-xl', 'border-b-4', 'border-button-primary', 'poet-card-hidden');
                poetCard.style.transitionDelay = `${index * 0.1}s`; // Staggered animation
                poetCard.innerHTML = `
                    <img src="${poet.image}" alt="صورة ${poet.name}" onerror="this.onerror=null;this.src='https://placehold.co/150x150/CCCCCC/666666?text=لا+صورة'"
                         class="w-32 h-32 rounded-full mx-auto mb-4 object-cover border-4 border-text-accent shadow-md">
                    <h3 class="text-2xl font-bold mb-2 text-dark-bg">${poet.name}</h3>
                    <button data-poet-id="${poet.id}"
                            class="view-poems-btn bg-button-primary hover:bg-button-hover text-white font-bold py-2 px-4 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                        عرض قصائده
                    </button>
                `;
                poetsGrid.appendChild(poetCard);
            });

            // Add Intersection Observer for animations
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.remove('poet-card-hidden');
                        entry.target.classList.add('poet-card-visible');
                        observer.unobserve(entry.target); // Stop observing once visible
                    }
                });
            }, { threshold: 0.1 }); // Trigger when 10% of item is visible

            document.querySelectorAll('.poet-card-hidden').forEach(card => {
                observer.observe(card);
            });


            // Add event listeners to the new buttons
            document.querySelectorAll('.view-poems-btn').forEach(button => {
                button.addEventListener('click', (event) => {
                    const poetId = event.target.dataset.poetId;
                    displayPoetDetail(poetId);
                });
            });
        }

        // Function to display poet detail page
        async function displayPoetDetail(poetId) {
            const poet = poetsData.find(p => p.id === poetId);
            if (!poet) {
                console.error('Poet not found:', poetId);
                return;
            }

            currentPoetId = poetId; // Set current poet

            poetDetailImage.src = poet.image;
            poetDetailImage.alt = `صورة ${poet.name}`;
            poetDetailName.textContent = poet.name;
            poetDetailBio.textContent = poet.bio;

            // Render poems for the default category (general)
            renderPoemsForPoet(poet.poems[currentPoemCategory] || []);

            // Highlight the default category button
            document.querySelectorAll('.category-btn').forEach(btn => {
                if (btn.dataset.category === currentPoemCategory) {
                    btn.classList.add('bg-text-accent', 'text-dark-bg');
                    btn.classList.remove('bg-button-primary', 'text-white');
                } else {
                    btn.classList.remove('bg-text-accent', 'text-dark-bg');
                    btn.classList.add('bg-button-primary', 'text-white');
                }
            });


            poetsPage.classList.add('hidden');
            poetDetailPage.classList.remove('hidden');
            window.scrollTo(0, 0); // Scroll to top of the page
        }

        // Function to render poems for the current poet based on category
        function renderPoemsForPoet(poemsToRender) {
            poemsList.innerHTML = ''; // Clear previous poems
            if (poemsToRender.length === 0) {
                poemsList.innerHTML = '<p class="text-center text-lg text-text-accent">لا توجد قصائد في هذه الفئة لهذا الشاعر حتى الآن.</p>';
                return;
            }
            poemsToRender.forEach(poem => {
                const listItem = document.createElement('li');
                listItem.classList.add('bg-light-bg', 'rounded-xl', 'shadow-md', 'p-5', 'cursor-pointer', 'hover:bg-gray-100', 'transition-colors', 'duration-200', 'border-l-4', 'border-text-accent');
                listItem.innerHTML = `
                    <h4 class="text-xl font-semibold text-dark-bg">${poem.title}</h4>
                `;
                listItem.addEventListener('click', () => showPoemModal(poem));
                poemsList.appendChild(listItem);
            });
        }

        // Function to show the poem modal
        async function showPoemModal(poem) {
            modalPoemTitle.textContent = poem.title;
            modalPoemText.textContent = ''; // Clear previous text
            modalLoader.style.display = 'block'; // Show loader
            poemModal.style.display = 'flex'; // Show modal

            const poetName = poetDetailName.textContent;
            // Construct the prompt for the LLM
            const prompt = `اكتب قصيدة بعنوان "${poem.title}" للشاعر ${poetName}. هذه القصيدة تنتمي إلى فئة "${currentPoemCategory === 'general' ? 'عامة' : currentPoemCategory}". إذا لم تكن القصيدة معروفة، فابتكر قصيدة ملهمة بهذا العنوان والأسلوب والجو العام الذي يتناسب مع الشاعر والفئة المحددة.`;

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
                    modalPoemText.textContent = 'تعذر تحميل القصيدة. يرجى المحاولة مرة أخرى.';
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

        // --- Event Listeners ---
        window.onload = () => {
            renderPoets(poetsData); // Render all poets on load
            currentYearSpan.textContent = new Date().getFullYear(); // Set current year in footer
        };

        // Main search input event
        mainSearchInput.addEventListener('input', (event) => {
            const searchTerm = event.target.value.toLowerCase();
            const filteredPoets = poetsData.filter(poet =>
                poet.name.toLowerCase().includes(searchTerm)
            );
            renderPoets(filteredPoets);
        });

        backToPoetsButton.addEventListener('click', showPoetsPage);

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

        // Poem category buttons event listeners
        document.querySelectorAll('.category-btn').forEach(button => {
            button.addEventListener('click', (event) => {
                // Remove active class from all buttons
                document.querySelectorAll('.category-btn').forEach(btn => {
                    btn.classList.remove('bg-text-accent', 'text-dark-bg');
                    btn.classList.add('bg-button-primary', 'text-white');
                });

                // Add active class to clicked button
                event.target.classList.add('bg-text-accent', 'text-dark-bg');
                event.target.classList.remove('bg-button-primary', 'text-white');

                currentPoemCategory = event.target.dataset.category;
                const currentPoet = poetsData.find(p => p.id === currentPoetId);
                if (currentPoet) {
                    renderPoemsForPoet(currentPoet.poems[currentPoemCategory] || []);
                }
            });
        });
    </script>
</body>
</html>

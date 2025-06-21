<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ديوان الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for Hamburger Icon and Search Icon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Define custom colors and font based on the new light background from the image */
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap'); /* A clear, bold Arabic font */
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* Secondary classic Arabic font for poems */

        :root {
            --light-cream-bg: #F5F5DC; /* Based on the new image, a light cream/off-white */
            --dark-text: #222831; /* Dark text for contrast on light background */
            --accent-blue: #00ADB5; /* Primary accent color */
            --accent-yellow: #FFD369; /* Secondary accent color */
            --footer-bg: #222831; /* Dark background for footer, as per image */
            --footer-text: #EEEEEE; /* Light text for footer */
        }

        body {
            font-family: 'Cairo', sans-serif;
            background-color: var(--light-cream-bg); /* Full site background */
            color: var(--dark-text);
            line-height: 1.8;
            scroll-behavior: smooth;
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--light-cream-bg);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--accent-blue);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-yellow);
        }

        /* --- Header Styles --- */
        .fixed-header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 50;
            background-color: var(--light-cream-bg);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-in-out;
            border-bottom: 1px solid rgba(0,0,0,0.1); /* Subtle separator */
        }

        .header-hidden {
            transform: translateY(-100%);
        }

        /* --- Hamburger Menu Sidebar Styles --- */
        .sidebar {
            height: 100%;
            width: 0;
            position: fixed;
            z-index: 100;
            top: 0;
            right: 0; /* From right for RTL */
            background-color: var(--dark-text); /* Dark background for sidebar */
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
            color: var(--footer-text); /* Light text on dark sidebar */
            display: block;
            transition: 0.3s;
            width: 100%;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .sidebar a:hover {
            color: var(--accent-yellow);
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
            transform: translateX(-50px);
        }

        .poet-card-visible {
            opacity: 1;
            transform: translateX(0);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        /* --- Poem Display Styles (Directly in main content) --- */
        .poem-container {
            background-color: #fcfcfc; /* Slightly different background for poem sections */
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            border-right: 4px solid var(--accent-blue);
        }

        .poem-title-inline {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--accent-blue);
            margin-bottom: 15px;
            border-bottom: 1px solid rgba(0,0,0,0.1);
            padding-bottom: 10px;
            text-align: center;
        }

        .poem-text-inline {
            font-family: 'Amiri', serif;
            font-size: 1.1rem;
            white-space: pre-line;
            text-align: justify;
            color: var(--dark-text);
        }

        @media (max-width: 768px) {
            .poem-text-inline {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body class="selection:bg-accent-yellow/50">

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
        <div class="flex items-center w-full">
            <h1 class="text-2xl sm:text-3xl font-extrabold text-accent-blue whitespace-nowrap mr-4">موسوعة الشعر العراقي</h1>
            <div class="relative flex-grow">
                <input type="text" id="main-search" placeholder="ابحث عن قصائد، شعراء..."
                       class="p-2 pr-10 border-2 border-accent-blue rounded-full focus:outline-none focus:ring-2 focus:ring-accent-yellow w-full text-lg text-right bg-light-cream-bg text-dark-text placeholder-gray-500">
                <i class="fa fa-search absolute right-3 top-1/2 -translate-y-1/2 text-gray-500"></i>
            </div>
            <button class="text-dark-text text-3xl sm:text-4xl p-2 rounded-lg hover:bg-gray-200 transition-colors mr-2" onclick="openNav()">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>
    <div class="h-[76px] sm:h-[84px]"></div> <!-- Placeholder for fixed header height -->

    <!-- Main Content Container -->
    <div class="container mx-auto px-4 sm:px-6 lg:px-8 pb-10">

        <!-- Poets Page (Default view) -->
        <section id="poets-page" class="py-10">
            <!-- Welcome Section -->
            <div class="bg-light-cream-bg rounded-2xl shadow-xl p-6 sm:p-10 mb-12 text-center border-b-4 border-accent-blue">
                <h2 class="text-4xl sm:text-5xl font-extrabold mb-4 text-dark-text leading-tight">مرحباً بك في موسوعة الشعر العراقي</h2>
                <p class="text-xl sm:text-2xl text-dark-text leading-relaxed max-w-3xl mx-auto">بوابة شاملة لأروع القصائد وأبرز الشعراء العراقيين</p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-accent-blue">الشعراء البارزون</h3>
            <div id="poets-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
                <!-- Poet cards will be rendered here by JavaScript -->
            </div>
        </section>

        <!-- Poet Detail Page (Hidden by default) -->
        <section id="poet-detail-page" class="py-10 hidden">
            <button id="back-to-poets"
                    class="mb-8 bg-accent-yellow hover:bg-accent-blue text-dark-text font-bold py-2 px-5 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                العودة إلى الشعراء
            </button>

            <div class="bg-light-cream-bg rounded-2xl shadow-xl p-8 mb-10 text-center border-b-4 border-accent-blue">
                <!-- Removed image, only name and bio -->
                <h2 id="poet-detail-name" class="text-4xl font-extrabold mb-4 text-dark-text"></h2>
                <p id="poet-detail-bio" class="text-lg leading-relaxed text-dark-text text-justify max-w-4xl mx-auto"></p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-accent-blue">قصائد الشاعر</h3>
            <div id="poem-categories" class="flex flex-wrap justify-center gap-3 mb-8">
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="general">عامة</button>
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="love">حب</button>
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="sadness">حزن</button>
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="longing">اشتياق</button>
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="joy">فرح</button>
                <button class="category-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-colors duration-200" data-category="wisdom">حكمة</button>
            </div>

            <div id="poems-display" class="space-y-6">
                <!-- Poems with titles and text will be rendered directly here -->
            </div>
            <div class="loader mx-auto mt-10" id="poems-loader"></div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="bg-footer-bg py-8 text-center shadow-inner mt-10">
        <div class="container mx-auto">
            <h4 class="text-footer-text text-3xl sm:text-4xl font-extrabold mb-4">موسوعة الشعر العراقي</h4>
            <p class="text-footer-text text-base leading-relaxed max-w-4xl mx-auto mb-6">
                بوابتك الشاملة لأروع قصائد الشعر الشعبي العراقي من عمالقة الشعر إلى الأصوات الشابة. نسعى لإثراء الساحة الأدبية وتقديم أرشيف متكامل يعكس جمال وعمق الكلمة العراقية.
            </p>
            <p class="text-footer-text text-sm mb-4">&copy; <span id="current-year"></span> كرار حيدر. جميع الحقوق محفوظة.</p>
            <div class="flex justify-center space-x-6 text-2xl text-footer-text">
                <a href="#" class="hover:text-accent-blue transition-colors"><i class="fab fa-facebook-f"></i></a>
                <a href="#" class="hover:text-accent-blue transition-colors"><i class="fab fa-twitter"></i></a>
                <a href="#" class="hover:text-accent-blue transition-colors"><i class="fab fa-instagram"></i></a>
                <a href="#" class="hover:text-accent-blue transition-colors"><i class="fab fa-youtube"></i></a>
                <a href="#" class="hover:text-accent-blue transition-colors"><i class="fab fa-telegram-plane"></i></a>
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
        // Data for poets and poems
        const poetsData = [
            {
                id: 'al_mutanabbi',
                name: 'أبو الطيب المتنبي',
                bio: 'هو أحمد بن الحسين الجعفي الكندي الكوفي أبو الطيب المتنبي. أحد أعظم شعراء العرب، ولد بالكوفة سنة 303 هـ وتوفي سنة 354 هـ. اشتهر بقوة لغته وفصاحته، وحكمته في شعره الذي تناول المدح والهجاء والرثاء والفخر والحكمة. يُعتبر شعره قمة الإبداع الأدبي العربي، وقد حفظ منه الكثير وصار مضرب الأمثال.',
                poems: {
                    general: [
                        { title: 'أنا الذي نظر الأعمى إلى أدبي' },
                        { title: 'على قدر أهل العزم تأتي العزائم' },
                        { title: 'وإذا كانت النفوس كباراً' }
                    ],
                    love: [
                        { title: 'أحبك لو كان حبي داءً' },
                        { title: 'فبتّ كأنني أسقى رضاباً' },
                        { title: 'مالي أكتِّم حباً' }
                    ],
                    sadness: [
                        { title: 'كفى بك داء أن ترى الموت شافيا' },
                        { title: 'ما كل ما يتمنى المرء يدركه' },
                        { title: 'لم أرى في عيوب الناس عيبا' }
                    ],
                    longing: [
                        { title: 'إذا ترحلت عن قوم وقد قدروا' },
                        { title: 'وحشتك يا سماء الشوق روحي' },
                        { title: 'بم التعلل لا أهل ولا وطن' }
                    ],
                    joy: [
                        { title: 'عيد بأي حال عدت يا عيد' },
                        { title: 'الخيل والليل والبيداء تعرفني' },
                        { title: 'إذا غامرت في شرف مروم' }
                    ],
                    wisdom: [
                        { title: 'ذو العقل يشقى في النعيم بعقله' },
                        { title: 'إذا أنت أكرمت الكريم ملكته' },
                        { title: 'كلما أنبت الزمان قناة' }
                    ]
                }
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير، معالجاً قضايا الوطن والإنسان بلغة شعرية متفردة.',
                poems: {
                    general: [
                        { title: 'أنشودة المطر' },
                        { title: 'مدينة بلا مطر' }
                    ],
                    love: [
                        { title: 'غريب على الخليج' },
                        { title: 'كانت لدي وردة' },
                        { title: 'صوت من الأعماق' }
                    ],
                    sadness: [
                        { title: 'المومس العمياء' },
                        { title: 'حفار القبور' },
                        { title: 'ليلة وداع' }
                    ],
                    longing: [
                        { title: 'رسالة إلى جيكور' },
                        { title: 'لأني غريب' },
                        { title: 'شمس الغريب' }
                    ],
                    joy: [
                        { title: 'أزهار و أساطير' },
                        { title: 'فجر' },
                        { title: 'أغنية للأرض' }
                    ],
                    wisdom: [
                        { title: 'أقوال من زمن قديم' },
                        { title: 'الشعر هو الحياة' },
                        { title: 'سر الوجود' }
                    ]
                }
            },
            {
                id: 'nazik_al_malaika',
                name: 'نازك الملائكة',
                bio: 'شاعرة عراقية وناقدة، ولدت في بغداد عام 1923 وتوفيت في القاهرة عام 2007. تُعد من أهم رواد الشعر الحر في الأدب العربي، إلى جانب بدر شاكر السياب وعبد الوهاب البياتي. تميزت قصائدها بجمال اللغة وعمق المعنى والفلسفة، وتناولت مواضيع الحرية والمرأة والحياة والموت.',
                poems: {
                    general: [
                        { title: 'الكوليرا' },
                        { title: 'عاشقة الليل' }
                    ],
                    love: [
                        { title: 'أنا والليل' },
                        { title: 'حبيبي يا ساكن الروح' },
                        { title: 'فجر الوفاء' }
                    ],
                    sadness: [
                        { title: 'شجرة القمر' },
                        { title: 'قنص المجهول' },
                        { title: 'نهاية المأساة' }
                    ],
                    longing: [
                        { title: 'وحدة' },
                        { title: 'المساء في القرية' },
                        { title: 'شوق بلا نهاية' }
                    ],
                    joy: [
                        { title: 'يوميات' },
                        { title: 'فرحة الألوان' },
                        { title: 'لحظات من السعادة' }
                    ],
                    wisdom: [
                        { title: 'في الطريق' },
                        { title: 'الشعر فن الحياة' },
                        { title: 'الزمن والحياة' }
                    ]
                }
            },
            {
                id: 'abd_al_wahhab',
                name: 'عبد الوهاب البياتي',
                bio: 'شاعر عراقي بارز من رواد حركة الشعر الحر، ولد في بغداد عام 1926 وتوفي في دمشق عام 1999. عرف بشعره الغزير والمتنوع الذي يجمع بين الواقعية والرمزية، ويعكس هموم الإنسان العربي وقضاياه الاجتماعية والسياسية، ويُعتبر صوته الشعري معبراً عن جيل بأكمله.',
                poems: {
                    general: [
                        { title: 'سوق القرية' },
                        { title: 'النار والكلمات' }
                    ],
                    love: [
                        { title: 'عينيها' },
                        { title: 'ألف ليلة وليلة' },
                        { title: 'أنشودة الحب' }
                    ],
                    sadness: [
                        { title: 'الذي يأتي ولا يأتي' },
                        { title: 'الموت في بغداد' },
                        { title: 'غيوم الحزن' }
                    ],
                    longing: [
                        { title: 'رحلة في أعماق الذاكرة' },
                        { title: 'نداء الروح' },
                        { title: 'حنين لا ينتهي' }
                    ],
                    joy: [
                        { title: 'إلى حبيبته' },
                        { title: 'فرحة العود' },
                        { title: 'لحن الأمل' }
                    ],
                    wisdom: [
                        { title: 'كتاب الفقر والثورة' },
                        { title: 'الحكمة الضائعة' },
                        { title: 'دروس الدهر' }
                    ]
                }
            },
            {
                id: 'jamil_sidqi',
                name: 'جميل صدقي الزهاوي',
                bio: 'شاعر وفيلسوف عراقي، ولد في بغداد عام 1863 وتوفي فيها عام 1936. يعتبر من أبرز شعراء العراق في العصر الحديث، واشتهر بشعره الذي يدعو إلى الإصلاح الاجتماعي والنهضة والحرية، وكان من دعاة تحرير المرأة. شعره اتسم بالجرأة الفكرية والأسلوب البليغ.',
                poems: {
                    general: [
                        { title: 'الخمر' },
                        { title: 'الزهاوي عن المرأة' }
                    ],
                    love: [
                        { title: 'غرامي المستحيل' },
                        { title: 'إلى حبيبتي' },
                        { title: 'نظرة عين' }
                    ],
                    sadness: [
                        { title: 'مرثية بغداد' },
                        { title: 'شكوى الزمن' },
                        { title: 'أطلال' }
                    ],
                    longing: [
                        { title: 'الشوق إلى الماضي' },
                        { title: 'أحن إليك' },
                        { title: 'ذكرى الأحباب' }
                    ],
                    joy: [
                        { title: 'بشائر العيد' },
                        { title: 'نشوة الحياة' },
                        { title: 'فرحة الأيام' }
                    ],
                    wisdom: [
                        { title: 'درس الحياة' },
                        { title: 'من أقوال الحكماء' },
                        { title: 'العقل والحياة' }
                    ]
                }
            },
            {
                id: 'ma_ruf_al_rusafi',
                name: 'معروف الرصافي',
                bio: 'شاعر عراقي كبير، ولد في بغداد عام 1875 وتوفي فيها عام 1945. يعد من رواد الشعر الحديث في العراق، وعرف بشعره الوطني والاجتماعي الذي يلامس قضايا الفقر والجهل والظلم، وكان له دور كبير في الصحافة العراقية، داعياً للعدالة والتعليم ومناهضة الاستبداد.',
                poems: {
                    general: [
                        { title: 'الأرملة المرضعة' },
                        { title: 'في دار الأيتام' }
                    ],
                    love: [
                        { title: 'أنت الحبيب' },
                        { title: 'همسة حب' },
                        { title: 'يا ليل العاشقين' }
                    ],
                    sadness: [
                        { title: 'وداع بغداد' },
                        { title: 'شكوى فلاح' },
                        { title: 'دموع على الرافدين' }
                    ],
                    longing: [
                        { title: 'حنين إلى الوطن' },
                        { title: 'يا بغداد لا تشجعي' },
                        { title: 'الغريب في وطنه' }
                    ],
                    joy: [
                        { title: 'تحية العيد' },
                        { title: 'بشائر النصر' },
                        { title: 'صباح الخير' }
                    ],
                    wisdom: [
                        { title: 'العلم والأخلاق' },
                        { title: 'الحياة دروس' },
                        { title: 'من وحي التجربة' }
                    ]
                }
            },
            {
                id: 'mohammad_mahdi_al_jawahiri',
                name: 'محمد مهدي الجواهري',
                bio: 'شاعر عربي عراقي يُلقب بـ "نهر العراق الثالث" و "شاعر العرب الأكبر". ولد في النجف عام 1899 وتوفي في دمشق عام 1997. يعتبر من أبرز شعراء العصر الحديث، وامتاز بغزارة إنتاجه وقوة أسلوبه وشاعريته الفذة التي غطت مختلف الأغراض الشعرية من وطنية وقومية ووجدانية.',
                poems: {
                    general: [
                        { title: 'يا دجلة الخير' },
                        { title: 'إلى أمي' }
                    ],
                    love: [
                        { title: 'أتتني ذات يوم' },
                        { title: 'حديث القلب' },
                        { title: 'أحلى النساء' }
                    ],
                    sadness: [
                        { title: 'ليلة وداع' },
                        { title: 'شكوى من الغربة' },
                        { title: 'أنا والغربة' }
                    ],
                    longing: [
                        { title: 'أيها الوطن' },
                        { title: 'الشوق إلى بغداد' },
                        { title: 'يا وطني' }
                    ],
                    joy: [
                        { title: 'ذكرى ثورة' },
                        { title: 'فرحة الأمل' },
                        { title: 'يوم النصر' }
                    ],
                    wisdom: [
                        { title: 'كن في الحياة' },
                        { title: 'فلسفة الحياة' },
                        { title: 'كلمات من ذهب' }
                    ]
                }
            },
            {
                id: 'abdul_ghani_al_raoui',
                name: 'عبد الغني الراوي',
                bio: 'شاعر عراقي معاصر، يُعرف بأسلوبه المميز الذي يجمع بين الأصالة والمعاصرة. ولد في العراق وله العديد من الدواوين الشعرية التي تتناول مواضيع متنوعة مثل الحب والوطن وقضايا الإنسان المعاصر، ويُعتبر صوته من الأصوات الشعرية الجديدة والمؤثرة في الساحة الأدبية العراقية.',
                poems: {
                    general: [
                        { title: 'بغداد الحبيبة' },
                        { title: 'نهر الحياة' }
                    ],
                    love: [
                        { title: 'عيناكِ سرُّ وجودي' },
                        { title: 'قصيدة حب أبدية' },
                        { title: 'أنتِ الأمل' }
                    ],
                    sadness: [
                        { title: 'وجع الروح' },
                        { title: 'دموع الفراق' },
                        { title: 'لحن الأسى' }
                    ],
                    longing: [
                        { title: 'شوق إلى الأمس' },
                        { title: 'حنين الوطن' },
                        { title: 'ذكرى الحبيب' }
                    ],
                    joy: [
                        { title: 'لحظة أمل' },
                        { title: 'ابتسامة الحياة' },
                        { title: 'نور جديد' }
                    ],
                    wisdom: [
                        { title: 'دروس الأيام' },
                        { title: 'حكمة الزمن' },
                        { title: 'بصيرة الحياة' }
                    ]
                }
            },
            {
                id: 'mustafa_jamal_al_din',
                name: 'مصطفى جمال الدين',
                bio: 'شاعر عراقي معاصر، ولد في النجف عام 1927 وتوفي في دمشق عام 1996. كان أستاذاً جامعياً وباحثاً لغوياً، وعرف بشعره الذي يجمع بين الأصالة والمعاصرة، وتميز بأسلوبه السلس والجميل، وله العديد من الدواوين الشعرية التي تتناول مواضيع وطنية واجتماعية.',
                poems: {
                    general: [
                        { title: 'بغداد يا قلعة الأسود' },
                        { title: 'رحيل' }
                    ],
                    love: [
                        { title: 'على شاطئ عينيك' },
                        { title: 'أحببتك' },
                        { title: 'نور عيني' }
                    ],
                    sadness: [
                        { title: 'أحزان النخيل' },
                        { title: 'الليل الحزين' },
                        { title: 'ذكرى الشهيد' }
                    ],
                    longing: [
                        { title: 'حنين إلى النجف' },
                        { title: 'يا دار الأحباب' },
                        { title: 'شوق إلى الماضي' }
                    ],
                    joy: [
                        { title: 'فرحة العودة' },
                        { title: 'عيد النصر' },
                        { title: 'ميلاد جديد' }
                    ],
                    wisdom: [
                        { title: 'فلسفة الحياة والموت' },
                        { title: 'العلم سلاح' },
                        { title: 'دروس الحياة' }
                    ]
                }
            },
            {
                id: 'lamia_abbas_amara',
                name: 'لميعة عباس عمارة',
                bio: 'شاعرة عراقية رائدة، ولدت في بغداد عام 1929. تُعد من أبرز شاعرات العراق في العصر الحديث، وامتازت قصائدها بالجرأة والجمال والرقة، وتناولت مواضيع الحب والمرأة والوطن بأسلوبها الخاص المميز.',
                poems: {
                    general: [
                        { title: 'مطر في بغداد' },
                        { title: 'نهران' }
                    ],
                    love: [
                        { title: 'أنت قدري' },
                        { title: 'رسائل حب' },
                        { title: 'عن العيون' }
                    ],
                    sadness: [
                        { title: 'حزني الساكن' },
                        { title: 'غياب القمر' },
                        { title: 'أيام الرحيل' }
                    ],
                    longing: [
                        { title: 'أشتاق إلى بغداد' },
                        { title: 'حنين السنين' },
                        { title: 'لا أريد شيئًا سوى الحب' }
                    ],
                    joy: [
                        { title: 'فرحة اللقاء' },
                        { title: 'ضحكة الشمس' },
                        { title: 'أمل جديد' }
                    ],
                    wisdom: [
                        { title: 'الزمن يعلمنا' },
                        { title: 'الحياة والأمل' },
                        { title: 'كلمات من القلب' }
                    ]
                }
            }
            // Add more poets as needed
        ];

        // Get DOM elements
        const poetsPage = document.getElementById('poets-page');
        const poetDetailPage = document.getElementById('poet-detail-page');
        const poetsGrid = document.getElementById('poets-grid');
        const mainSearchInput = document.getElementById('main-search');
        const backToPoetsButton = document.getElementById('back-to-poets');

        const poetDetailName = document.getElementById('poet-detail-name');
        const poetDetailBio = document.getElementById('poet-detail-bio');
        const poemsDisplay = document.getElementById('poems-display'); // This will hold both titles and texts
        const poemCategoriesContainer = document.getElementById('poem-categories');
        const poemsLoader = document.getElementById('poems-loader');

        const mySidebar = document.getElementById("mySidebar");
        const mainHeader = document.getElementById("main-header");
        const currentYearSpan = document.getElementById("current-year");

        let currentPoetId = null;
        let currentPoemCategory = 'general';

        // --- Hamburger Menu Logic ---
        function openNav() {
            mySidebar.style.width = "250px";
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
                closeNav();
            } else {
                // Scrolling up
                mainHeader.classList.remove('header-hidden');
            }
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop;
        });

        // --- Page Navigation Functions ---
        function showPoetsPage() {
            poetDetailPage.classList.add('hidden');
            poetsPage.classList.remove('hidden');
            mainSearchInput.value = '';
            renderPoets(poetsData);
            closeNav();
            window.scrollTo(0, 0);
        }

        function showCategory(category) {
            closeNav();
            // This would navigate to a category-specific page, or filter poets by category
            alert(`سيتم عرض قصائد من فئة: ${category === 'love' ? 'الحب' : category === 'sadness' ? 'الحزن' : category === 'longing' ? 'الاشتياق' : category === 'joy' ? 'الفرح' : category === 'wisdom' ? 'الحكمة' : 'عامة'}. هذا القسم قيد الإنشاء!`);
            showPoetsPage(); // For now, return to poets page
        }

        // --- Poet Card Rendering and Animations ---
        function renderPoets(poetsToRender) {
            poetsGrid.innerHTML = '';
            if (poetsToRender.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-xl text-accent-blue">لا توجد نتائج مطابقة.</p>';
                return;
            }
            poetsToRender.forEach((poet, index) => {
                const poetCard = document.createElement('div');
                poetCard.classList.add('bg-light-cream-bg', 'rounded-2xl', 'shadow-lg', 'p-6', 'text-center', 'transform', 'transition-transform', 'duration-300', 'hover:scale-105', 'hover:shadow-xl', 'border-b-4', 'border-accent-blue', 'poet-card-hidden');
                poetCard.style.transitionDelay = `${index * 0.1}s`;
                poetCard.innerHTML = `
                    <h3 class="text-2xl font-bold mb-4 text-dark-text">${poet.name}</h3>
                    <button data-poet-id="${poet.id}"
                            class="view-poems-btn bg-accent-blue hover:bg-accent-yellow text-white font-bold py-2 px-4 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                        عرض قصائده
                    </button>
                `;
                poetsGrid.appendChild(poetCard);
            });

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.remove('poet-card-hidden');
                        entry.target.classList.add('poet-card-visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.poet-card-hidden').forEach(card => {
                observer.observe(card);
            });

            document.querySelectorAll('.view-poems-btn').forEach(button => {
                button.addEventListener('click', (event) => {
                    const poetId = event.target.dataset.poetId;
                    displayPoetDetail(poetId);
                });
            });
        }

        // Function to display poet detail page and load poems directly
        async function displayPoetDetail(poetId) {
            const poet = poetsData.find(p => p.id === poetId);
            if (!poet) {
                console.error('Poet not found:', poetId);
                return;
            }

            currentPoetId = poetId;
            currentPoemCategory = 'general'; // Reset to general when changing poet

            poetDetailName.textContent = poet.name;
            poetDetailBio.textContent = poet.bio;

            // Highlight the default category button ('general')
            document.querySelectorAll('.category-btn').forEach(btn => {
                if (btn.dataset.category === 'general') {
                    btn.classList.add('bg-accent-yellow', 'text-dark-text');
                    btn.classList.remove('bg-accent-blue', 'text-white');
                } else {
                    btn.classList.remove('bg-accent-yellow', 'text-dark-text');
                    btn.classList.add('bg-accent-blue', 'text-white');
                }
            });

            poetsPage.classList.add('hidden');
            poetDetailPage.classList.remove('hidden');
            window.scrollTo(0, 0);

            // Directly render and load poems for the default category
            await renderAndLoadPoems(poet.poems[currentPoemCategory] || []);
        }

        // Function to render poem titles and fetch/display their content
        async function renderAndLoadPoems(poemsToRender) {
            poemsDisplay.innerHTML = ''; // Clear previous poems
            poemsLoader.style.display = 'block'; // Show loader

            if (poemsToRender.length === 0) {
                poemsDisplay.innerHTML = '<p class="text-center text-lg text-dark-text">لا توجد قصائد في هذه الفئة لهذا الشاعر حتى الآن.</p>';
                poemsLoader.style.display = 'none'; // Hide loader
                return;
            }

            for (const poem of poemsToRender) {
                const poemDiv = document.createElement('div');
                poemDiv.classList.add('poem-container');
                poemsDisplay.appendChild(poemDiv);

                const poemTitleElement = document.createElement('h4');
                poemTitleElement.classList.add('poem-title-inline');
                poemTitleElement.textContent = poem.title;
                poemDiv.appendChild(poemTitleElement);

                const poemTextElement = document.createElement('p');
                poemTextElement.classList.add('poem-text-inline');
                poemTextElement.textContent = 'جاري تحميل القصيدة...'; // Initial loading text
                poemDiv.appendChild(poemTextElement);

                // Fetch poem content from LLM
                const poetName = poetDetailName.textContent;
                const prompt = `اكتب قصيدة بعنوان "${poem.title}" للشاعر ${poetName}. هذه القصيدة تنتمي إلى فئة "${currentPoemCategory === 'general' ? 'عامة' : currentPoemCategory}". إذا لم تكن القصيدة معروفة، فابتكر قصيدة ملهمة بهذا العنوان والأسلوب والجو العام الذي يتناسب مع الشاعر والفئة المحددة. يجب أن تكون القصيدة كافية ومعبرة، حوالي 5-10 أبيات.`;

                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: prompt }] });
                const payload = { contents: chatHistory };
                const apiKey = "";
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
                        poemTextElement.textContent = generatedText;
                    } else {
                        poemTextElement.textContent = 'تعذر تحميل القصيدة. يرجى المحاولة مرة أخرى.';
                        console.error('API response error:', result);
                    }
                } catch (error) {
                    poemTextElement.textContent = 'حدث خطأ أثناء تحميل القصيدة. يرجى التحقق من اتصالك بالإنترنت.';
                    console.error('Fetch error:', error);
                }
                // Small delay to make loading visible for each poem
                await new Promise(resolve => setTimeout(resolve, 300));
            }
            poemsLoader.style.display = 'none'; // Hide loader after all poems are loaded
        }

        // --- Event Listeners ---
        window.onload = () => {
            renderPoets(poetsData);
            currentYearSpan.textContent = new Date().getFullYear();
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

        // Poem category buttons event listeners
        document.querySelectorAll('.category-btn').forEach(button => {
            button.addEventListener('click', async (event) => {
                // Remove active class from all buttons
                document.querySelectorAll('.category-btn').forEach(btn => {
                    btn.classList.remove('bg-accent-yellow', 'text-dark-text');
                    btn.classList.add('bg-accent-blue', 'text-white');
                });

                // Add active class to clicked button
                event.target.classList.add('bg-accent-yellow', 'text-dark-text');
                event.target.classList.remove('bg-accent-blue', 'text-white');

                currentPoemCategory = event.target.dataset.category;
                const currentPoet = poetsData.find(p => p.id === currentPoetId);
                if (currentPoet) {
                    await renderAndLoadPoems(currentPoet.poems[currentPoemCategory] || []);
                }
            });
        });
    </script>
</body>
</html>

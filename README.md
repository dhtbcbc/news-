<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ديوان الشعر العراقي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Define custom colors and font based on the suggestions */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&display=swap'); /* A classic Arabic font */

        :root {
            --bg-light-beige: #FAF8F4; /* Suggested warm beige */
            --text-dark-charcoal: #36454F; /* Suggested dark charcoal */
            --accent-turquoise: #40E0D0; /* Suggested subtle turquoise */
            --accent-golden: #DAA520; /* Suggested golden for accents */
            --accent-burnt-orange: #CD5C5C; /* Suggested burnt orange for accents */
        }

        body {
            font-family: 'Amiri', 'Inter', sans-serif; /* Prioritize Arabic font */
            background-color: var(--bg-light-beige);
            color: var(--text-dark-charcoal);
            line-height: 1.8; /* Improve readability for Arabic text */
        }

        /* Custom scrollbar for better aesthetics */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-light-beige);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--accent-turquoise);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-golden);
        }

        /* Basic modal styles (for showing poem text) */
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
            background-color: var(--bg-light-beige);
            margin: auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            max-width: 800px;
            width: 90%;
            position: relative;
            max-height: 90vh; /* Max height for scrolling content */
            overflow-y: auto; /* Enable scrolling for poem content */
            text-align: center; /* Center poem lines */
            direction: rtl; /* Ensure Arabic text is right-to-left */
        }

        .close-button {
            color: var(--text-dark-charcoal);
            font-size: 36px;
            font-weight: bold;
            position: absolute;
            top: 10px;
            right: 20px;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: var(--accent-burnt-orange);
            text-decoration: none;
            cursor: pointer;
        }

        .poem-title-modal {
            font-size: 2rem;
            font-weight: bold;
            color: var(--accent-turquoise);
            margin-bottom: 20px;
            border-bottom: 2px solid var(--accent-golden);
            padding-bottom: 10px;
        }

        .poem-text-modal {
            font-size: 1.2rem;
            white-space: pre-line; /* Preserves line breaks from data */
            text-align: justify; /* Justify text for better readability */
            margin-top: 20px;
        }

        /* Responsive adjustments for poem text */
        @media (max-width: 768px) {
            .poem-text-modal {
                font-size: 1rem;
            }
        }

        /* Loading indicator styles */
        .loader {
            border: 6px solid #f3f3f3; /* Light grey */
            border-top: 6px solid var(--accent-turquoise); /* Blue */
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
<body class="selection:bg-accent-golden/50">
    <!-- Main Container -->
    <div class="container mx-auto p-4 sm:p-6 lg:p-8">
        <!-- Poets Page (Default view) -->
        <section id="poets-page" class="py-10">
            <h1 class="text-5xl font-extrabold text-center mb-10 text-accent-turquoise drop-shadow-lg">ديوان الشعر العراقي</h1>
            <p class="text-xl text-center mb-12 max-w-2xl mx-auto leading-relaxed">استكشف كنوز الشعر العراقي الخالدة من كبار الشعراء.</p>

            <div class="flex flex-col sm:flex-row items-center justify-center mb-12 gap-4">
                <input type="text" id="poet-search" placeholder="ابحث عن شاعر..."
                       class="p-3 border-2 border-accent-turquoise rounded-full focus:outline-none focus:ring-2 focus:ring-accent-golden w-full sm:w-80 text-lg text-right shadow-md">
                <button id="search-button"
                        class="bg-accent-turquoise hover:bg-accent-golden text-white font-bold py-3 px-6 rounded-full transition-all duration-300 transform hover:scale-105 shadow-lg">
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
                    class="mb-8 bg-accent-golden hover:bg-accent-burnt-orange text-white font-bold py-2 px-5 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                العودة إلى الشعراء
            </button>

            <div class="bg-white rounded-2xl shadow-xl p-8 mb-10 text-center border-b-4 border-accent-turquoise">
                <img id="poet-detail-image" src="" alt="صورة الشاعر" class="w-40 h-40 rounded-full mx-auto mb-6 object-cover border-4 border-accent-golden shadow-lg">
                <h2 id="poet-detail-name" class="text-4xl font-extrabold mb-4 text-accent-turquoise"></h2>
                <p id="poet-detail-bio" class="text-lg leading-relaxed text-text-dark-charcoal text-justify max-w-4xl mx-auto"></p>
            </div>

            <h3 class="text-3xl font-bold text-center mb-8 text-accent-golden">قصائد الشاعر</h3>
            <div class="flex items-center justify-center mb-8">
                <input type="text" id="poem-search" placeholder="ابحث عن قصيدة..."
                       class="p-3 border-2 border-accent-turquoise rounded-full focus:outline-none focus:ring-2 focus:ring-accent-golden w-full sm:w-96 text-lg text-right shadow-md">
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

    <script>
        // Placeholder data for poets and poems
        // In a real application, this would come from a database or API
        const poetsData = [
            {
                id: 'al_mutanabbi',
                name: 'أبو الطيب المتنبي',
                image: 'https://placehold.co/150x150/DAA520/ffffff?text=المتنبي',
                bio: 'هو أحمد بن الحسين الجعفي الكندي الكوفي أبو الطيب المتنبي. أحد أعظم شعراء العرب، ولد بالكوفة سنة 303 هـ وتوفي سنة 354 هـ. اشتهر بقوة لغته وفصاحته، وحكمته في شعره الذي تناول المدح والهجاء والرثاء والفخر والحكمة.',
                poems: [
                    { title: 'أنا الذي نظر الأعمى إلى أدبي', text: `أنا الذي نظر الأعمى إلى أدبي\nوأسمعت كلماتي من به صمم\nالخيل والليل والبيداء تعرفني\nوالسيف والرمح والقرطاس والقلم` },
                    { title: 'على قدر أهل العزم تأتي العزائم', text: `على قدر أهل العزم تأتي العزائم\nوتأتي على قدر الكرام المكارم\nوتكبر في عين الصغير صغارها\nوتصغر في عين العظيم العظائم` },
                    { title: 'وإذا كانت النفوس كباراً', text: `وإذا كانت النفوس كباراً\nتعبت في مرادها الأجسام` }
                ]
            },
            {
                id: 'badr_shaker',
                name: 'بدر شاكر السياب',
                image: 'https://placehold.co/150x150/40E0D0/ffffff?text=السياب',
                bio: 'شاعر عراقي رائد من رواد الشعر الحر، ولد في قرية جيكور بالبصرة عام 1926 وتوفي في الكويت عام 1964. يعتبر من أهم مؤسسي حركة الشعر الحر في الأدب العربي، وأثرى المكتبة العربية بقصائده العميقة التي تتناول الواقع والمعاناة والأساطير.',
                poems: [
                    { title: 'أنشودة المطر', text: `عيناكِ غابتا نخيلٍ ساعةَ السَحَرْ\nأو شُرفتانِ راحَ يَنأى عنهما القَمَرْ\nعيناكِ حينما تَبتسِمانِ تورقُ الكرومْ\nوتَرقصُ الأضواءُ... كالأقمارِ في نَهَرْ` },
                    { title: 'مدينة بلا مطر', text: `أمطري أيتها السحب\nمن دمي أيتها السحب\nمن تراب أحبائي أمطري` }
                ]
            },
            {
                id: 'nazik_al_malaika',
                name: 'نازك الملائكة',
                image: 'https://placehold.co/150x150/CD5C5C/ffffff?text=نازك',
                bio: 'شاعرة عراقية وناقدة، ولدت في بغداد عام 1923 وتوفيت في القاهرة عام 2007. تُعد من أهم رواد الشعر الحر في الأدب العربي، إلى جانب بدر شاكر السياب وعبد الوهاب البياتي. تميزت قصائدها بجمال اللغة وعمق المعنى والفلسفة.',
                poems: [
                    { title: 'الكوليرا', text: `الليلُ يسألُ من عتمتِهْ\nمنْ سيعودُ مِنَ السَفَرِ؟\nمن سيُفَرِّقُ هذه الظُلَمَةْ؟\nمن سيُفَتِّحُ هذا السِتْرَ؟` },
                    { title: 'عاشقة الليل', text: `الليل سِحرٌ والقلوب هواه\nوالنجم يُبدي للعيون سناه` }
                ]
            },
            {
                id: 'abd_al_wahhab',
                name: 'عبد الوهاب البياتي',
                image: 'https://placehold.co/150x150/DAA520/ffffff?text=البياتي',
                bio: 'شاعر عراقي بارز من رواد حركة الشعر الحر، ولد في بغداد عام 1926 وتوفي في دمشق عام 1999. عرف بشعره الغزير والمتنوع الذي يجمع بين الواقعية والرمزية، ويعكس هموم الإنسان العربي وقضاياه الاجتماعية والسياسية.',
                poems: [
                    { title: 'سوق القرية', text: `في سوق القريةِ ماتتْ\nشمسٌ وبقيتْ ظلالْ\nوالصمتُ يلفّ الكونْ\nوالريحُ حكايا وأمثالْ` },
                    { title: 'النار والكلمات', text: `النارُ تلتهمُ الحطبْ\nوالكلماتُ تلتهمُ القلوبْ` }
                ]
            },
            {
                id: 'jamil_sidqi',
                name: 'جميل صدقي الزهاوي',
                image: 'https://placehold.co/150x150/40E0D0/ffffff?text=الزهاوي',
                bio: 'شاعر وفيلسوف عراقي، ولد في بغداد عام 1863 وتوفي فيها عام 1936. يعتبر من أبرز شعراء العراق في العصر الحديث، واشتهر بشعره الذي يدعو إلى الإصلاح الاجتماعي والنهضة والحرية، وكان من دعاة تحرير المرأة.',
                poems: [
                    { title: 'الخمر', text: `صَهباءُ لا تَخشى سُكونَ الرّاحِ\nماذا تُحاولُ مِن وِدادِ قِداحِ` },
                    { title: 'الزهاوي عن المرأة', text: `يا ربّاتِ الخِدْرِ يا بناتِ\nيا مِثالاً للقُوّةِ الذاتيّةِ` }
                ]
            },
            {
                id: 'ma_ruf_al_rusafi',
                name: 'معروف الرصافي',
                image: 'https://placehold.co/150x150/CD5C5C/ffffff?text=الرصافي',
                bio: 'شاعر عراقي كبير، ولد في بغداد عام 1875 وتوفي فيها عام 1945. يعد من رواد الشعر الحديث في العراق، وعرف بشعره الوطني والاجتماعي الذي يلامس قضايا الفقر والجهل والظلم، وكان له دور كبير في الصحافة العراقية.',
                poems: [
                    { title: 'الأرملة المرضعة', text: `يا أُخْتَ رَحْمَتِها يا أُمَّ بائسَةٍ\nدَاءُ الضَنَى في فؤادٍ مِنْكِ قَدْ سَكَنَا` },
                    { title: 'في دار الأيتام', text: `إنّ اليَتِيمَ يُسَاءُ حالُهُ\nويُحْمَلُ الظُلْمُ والأَذَى` }
                ]
            }
        ];

        // Get DOM elements
        const poetsPage = document.getElementById('poets-page');
        const poetDetailPage = document.getElementById('poet-detail-page');
        const poetsGrid = document.getElementById('poets-grid');
        const poetSearchInput = document.getElementById('poet-search');
        const searchButton = document.getElementById('search-button');
        const backToPoetsButton = document.getElementById('back-to-poets');

        const poetDetailImage = document.getElementById('poet-detail-image');
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

        // Function to render poet cards
        function renderPoets(poetsToRender) {
            poetsGrid.innerHTML = ''; // Clear previous poets
            if (poetsToRender.length === 0) {
                poetsGrid.innerHTML = '<p class="col-span-full text-center text-xl text-red-500">لا توجد نتائج مطابقة.</p>';
                return;
            }
            poetsToRender.forEach(poet => {
                const poetCard = document.createElement('div');
                poetCard.classList.add('bg-white', 'rounded-2xl', 'shadow-lg', 'p-6', 'text-center', 'transform', 'transition-transform', 'duration-300', 'hover:scale-105', 'hover:shadow-xl', 'border-b-4', 'border-accent-golden');
                poetCard.innerHTML = `
                    <img src="${poet.image}" alt="صورة ${poet.name}" onerror="this.onerror=null;this.src='https://placehold.co/150x150/CCCCCC/666666?text=لا+صورة'"
                         class="w-32 h-32 rounded-full mx-auto mb-4 object-cover border-4 border-accent-turquoise shadow-md">
                    <h3 class="text-2xl font-bold mb-2 text-text-dark-charcoal">${poet.name}</h3>
                    <button data-poet-id="${poet.id}"
                            class="view-poems-btn bg-accent-turquoise hover:bg-accent-golden text-white font-bold py-2 px-4 rounded-full transition-all duration-300 transform hover:scale-105 shadow-md">
                        عرض قصائده
                    </button>
                `;
                poetsGrid.appendChild(poetCard);
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

            renderPoemsForPoet(poet.poems);

            poetsPage.classList.add('hidden');
            poetDetailPage.classList.remove('hidden');
            window.scrollTo(0, 0); // Scroll to top of the page
        }

        // Function to render poems for the current poet
        function renderPoemsForPoet(poemsToRender) {
            poemsList.innerHTML = ''; // Clear previous poems
            if (poemsToRender.length === 0) {
                poemsList.innerHTML = '<p class="text-center text-lg text-gray-600">لا توجد قصائد لهذا الشاعر حتى الآن.</p>';
                return;
            }
            poemsToRender.forEach(poem => {
                const listItem = document.createElement('li');
                listItem.classList.add('bg-white', 'rounded-xl', 'shadow-md', 'p-5', 'cursor-pointer', 'hover:bg-gray-50', 'transition-colors', 'duration-200', 'border-l-4', 'border-accent-turquoise');
                listItem.innerHTML = `
                    <h4 class="text-xl font-semibold text-text-dark-charcoal">${poem.title}</h4>
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

            // Simulate API call for poem content (replace with actual fetch in real app)
            // Call LLM for generating poem text.
            let chatHistory = [];
            chatHistory.push({ role: "user", parts: [{ text: `القصيدة بعنوان "${poem.title}" للشاعر ${poetDetailName.textContent}. اكتب هذه القصيدة كاملة. إذا لم تكن موجودة، قم بإنشاء قصيدة ملهمة بهذا العنوان بنفس أسلوب الشاعر.` }] });
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

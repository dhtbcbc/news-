import React, { useState, useEffect } from 'react';

// --- بيانات الشعراء والقصائد الأولية ---
// ملاحظة: في تطبيق حقيقي، ستأتي هذه البيانات من قاعدة بيانات.
const initialPoetsData = [
    {
        id: 1,
        name: "سمير صبيح",
        bio: "أحد أبرز شعراء الأغنية والقصيدة الشعبية في العراق، ولد في بغداد عام 1970 وتوفي عام 2022. تميز بأسلوبه العذب وقصائده التي لامست قلوب الملايين.",
        imageUrl: "https://placehold.co/400x400/8B5E3C/FAF9F6?text=Samir+Subaih",
        poems: [
            {
                id: 101,
                title: "يا روحي وكياني",
                category: "غزل",
                content: `يا روحي وكياني... يا كل عمري ... يا دنيتي... يا لغايـب
شميت عطرك وانسيت روحي... يا دنيا ويا هلي يا نور عيني
وساكن بفكري...
أشتاك لعيونك... ولنظراتك... ولهمساتك... ولضحكاتك
لو تدري بغيابك شسوه بيه... ما فاركتني لحظة...
أنت النفس اللي يصعد وينزل بيه... وأنت الدم اللي يجري بشراييني`
            },
            {
                id: 102,
                title: "تمنيت",
                category: "عتاب",
                content: `تمنيت القبر يوسع الاثنين
جا مكتوب عالميت عاشك
جا خضر ورد فوك القبر غافي
ومنقوشه الحروف بقطعة صافي
انا تمنيت من اشتاك ما احجي
بس عيوني تحجي البيه كلشي`
            }
        ]
    },
    {
        id: 2,
        name: "جبار رشيد",
        bio: "شاعر عراقي من مواليد بغداد، اشتهر بقصائده الوجدانية الجريئة وأسلوبه المميز في الإلقاء. يعتبر من الأصوات الشعرية الحديثة والمؤثرة.",
        imageUrl: "https://placehold.co/400x400/EEDC82/8B5E3C?text=Jabbar+Rasheed",
        poems: [
            {
                id: 201,
                title: "عطر المحبة",
                category: "حب",
                content: `شعندك يا حزن من الصبح وياي؟
هو اني كاضيها بس قهر وياك
ما مرتاح منك يوم
ولا ليلة بغيابك نوم
صرت انت الهوا والماي`
            },
            {
                id: 202,
                title: "لا تسولف",
                category: "جريء",
                content: `لا تسولف واضح شرايد تكول
عيونك تحجي كلشي قبل الشفايف
لا تكلي تغيرت انت هواي
اعرف طباعك واعرفك ما تخالف`
            }
        ]
    },
    {
        id: 3,
        name: "علي رشم",
        bio: "شاعر شعبي عراقي شاب، ولد في بغداد عام 1988 وتوفي عام 2015. كان مقاتلاً في الحشد الشعبي، واشتهر بقصائده الوطنية والوجدانية التي عكست روحه الشابة.",
        imageUrl: "https://placehold.co/400x400/FFA500/FAF9F6?text=Ali+Rashem",
        poems: [
            {
                id: 301,
                title: "وصيتي",
                category: "وطني",
                content: `اذا مرتاح هسه بدوني ضل مرتاح
اهم شي راحتك لو حته من دوني
بس مشتاكلك مو بيدي والله شلون
ذبحتني عليك تريدك عيوني`
            },
        ]
    },
    {
        id: 4,
        name: "مظفر النواب",
        bio: "شاعر عراقي كبير ومعارض سياسي، ولد في بغداد عام 1934 وتوفي عام 2022. يعتبر من أهم الأصوات في الشعر العربي الحديث، وتميز بشعره الثوري والوجداني العميق.",
        imageUrl: "https://placehold.co/400x400/4A2E2A/FAF9F6?text=Muzzafar+Al-Nawab",
        poems: [
            {
                id: 401,
                title: "يا حزن",
                category: "حزن",
                content: `يا حزن... يا بيوتنا المعتمة بليل الشتا
يا حزن... يا حجاية أمي الما تفض
يا حزن... يا دمعة بعيون الجهال
يا حزن... يا كل درابين العراق التنتظر جية الفرح`
            },
            {
                id: 402,
                title: "بالريل",
                category: "وجداني",
                content: `مرينا بيكم حمد واحنا بقطار الليل
وسمعنا دك كهوة وشمينا ريحة هيل
يا ريل صيح بقهر صيحة عشگ يا ريل
هودر هواهم ولك حدر السنابل جات`
            }
        ]
    }
];

// --- مكونات واجهة المستخدم ---

// أيقونة البحث
const SearchIcon = () => (
    <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
    </svg>
);

// أيقونة الرجوع
const BackIcon = () => (
    <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6 ml-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M17 8l4 4m0 0l-4 4m4-4H3" />
    </svg>
);

// رأس الصفحة
const Header = ({ onSearch, searchQuery }) => (
    <header className="bg-stone-800 text-stone-100 shadow-lg p-4 sticky top-0 z-50">
        <div className="container mx-auto flex justify-between items-center flex-wrap gap-4">
            <h1 className="text-3xl font-bold font-[serif] text-amber-400">ديوان الشعر العراقي</h1>
            <div className="relative w-full md:w-1/3">
                <input
                    type="text"
                    placeholder="ابحث عن شاعر أو قصيدة..."
                    value={searchQuery}
                    onChange={(e) => onSearch(e.target.value)}
                    className="w-full bg-stone-700 text-white placeholder-stone-400 rounded-full py-2 pr-10 pl-4 focus:outline-none focus:ring-2 focus:ring-amber-400 transition"
                />
                <div className="absolute top-1/2 right-3 -translate-y-1/2 text-stone-400">
                    <SearchIcon />
                </div>
            </div>
        </div>
    </header>
);

// بطاقة الشاعر
const PoetCard = ({ poet, onSelectPoet }) => (
    <div
        className="bg-stone-100 rounded-lg shadow-md overflow-hidden transform hover:-translate-y-2 transition-transform duration-300 cursor-pointer"
        onClick={() => onSelectPoet(poet)}
    >
        <img src={poet.imageUrl} alt={poet.name} className="w-full h-56 object-cover" />
        <div className="p-4 text-center">
            <h3 className="text-2xl font-semibold text-stone-800">{poet.name}</h3>
        </div>
    </div>
);

// الصفحة الرئيسية
const HomePage = ({ poets, onSelectPoet, filteredPoets }) => (
    <main className="container mx-auto p-6">
        <section id="poets" className="mb-12">
            <h2 className="text-4xl font-bold text-stone-700 mb-8 text-center border-b-2 border-amber-400 pb-2">أبرز الشعراء</h2>
            {filteredPoets.length > 0 ? (
                <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
                    {filteredPoets.map(poet => <PoetCard key={poet.id} poet={poet} onSelectPoet={onSelectPoet} />)}
                </div>
            ) : (
                <p className="text-center text-stone-500 text-xl">لم يتم العثور على شعراء يطابقون بحثك.</p>
            )}
        </section>
    </main>
);

// صفحة الشاعر
const PoetPage = ({ poet, onSelectPoem, onBack }) => (
    <div className="container mx-auto p-6 animate-fade-in">
        <button onClick={onBack} className="mb-8 flex items-center text-lg font-semibold text-stone-600 hover:text-amber-500 transition">
            <BackIcon />
            <span>العودة إلى قائمة الشعراء</span>
        </button>
        <div className="flex flex-col md:flex-row gap-8 items-start">
            <div className="md:w-1/3 text-center">
                <img src={poet.imageUrl} alt={poet.name} className="w-full rounded-lg shadow-xl mx-auto" />
                <h2 className="text-4xl font-bold mt-4 text-stone-800">{poet.name}</h2>
            </div>
            <div className="md:w-2/3">
                <p className="text-lg text-stone-600 leading-relaxed mb-8">{poet.bio}</p>
                <h3 className="text-3xl font-bold text-stone-700 mb-4 border-b-2 border-amber-400 pb-2">قصائده</h3>
                <ul className="space-y-3">
                    {poet.poems.map(poem => (
                        <li key={poem.id}>
                            <a onClick={() => onSelectPoem(poem)} className="text-xl text-stone-800 hover:text-amber-600 cursor-pointer transition">
                                - {poem.title}
                            </a>
                        </li>
                    ))}
                </ul>
            </div>
        </div>
    </div>
);


// صفحة القصيدة
const PoemPage = ({ poem, poetName, onBack }) => {
    const copyToClipboard = () => {
        const poemText = `قصيدة: ${poem.title}\nللشاعر: ${poetName}\n\n${poem.content}`;
        navigator.clipboard.writeText(poemText).then(() => {
            alert("تم نسخ القصيدة بنجاح!");
        }).catch(err => {
            console.error('Failed to copy text: ', err);
        });
    };

    return (
        <div className="container mx-auto p-6 animate-fade-in">
            <button onClick={onBack} className="mb-8 flex items-center text-lg font-semibold text-stone-600 hover:text-amber-500 transition">
                <BackIcon />
                <span>العودة إلى قصائد الشاعر</span>
            </button>
            <div className="bg-white p-8 rounded-lg shadow-xl">
                <h2 className="text-4xl font-bold text-stone-800 mb-2">{poem.title}</h2>
                <p className="text-xl text-stone-500 mb-6">للشاعر: {poetName}</p>
                <p className="text-2xl text-stone-700 whitespace-pre-wrap leading-loose font-[serif]">
                    {poem.content}
                </p>
                <div className="text-center mt-8">
                    <button onClick={copyToClipboard} className="bg-amber-500 text-white font-bold py-2 px-6 rounded-full hover:bg-amber-600 transition duration-300">
                        نسخ القصيدة
                    </button>
                </div>
            </div>
        </div>
    );
};


// المكون الرئيسي للتطبيق
export default function App() {
    const [poets, setPoets] = useState(initialPoetsData);
    const [searchQuery, setSearchQuery] = useState('');
    const [selectedPoet, setSelectedPoet] = useState(null);
    const [selectedPoem, setSelectedPoem] = useState(null);

    // دالة للبحث
    const filteredPoets = poets.filter(poet =>
        poet.name.toLowerCase().includes(searchQuery.toLowerCase()) ||
        poet.poems.some(poem => poem.title.toLowerCase().includes(searchQuery.toLowerCase()))
    );

    // التنقل بين الصفحات
    const handleSelectPoet = (poet) => {
        setSelectedPoet(poet);
        setSelectedPoem(null);
    };

    const handleSelectPoem = (poem) => {
        setSelectedPoem(poem);
    };

    const goHome = () => {
        setSelectedPoet(null);
        setSelectedPoem(null);
    };

    const goToPoetPage = () => {
        setSelectedPoem(null);
    }
    
    // العرض بناءً على الحالة
    const renderContent = () => {
        if (selectedPoet && selectedPoem) {
            return <PoemPage poem={selectedPoem} poetName={selectedPoet.name} onBack={goToPoetPage} />;
        }
        if (selectedPoet) {
            return <PoetPage poet={selectedPoet} onSelectPoem={handleSelectPoem} onBack={goHome} />;
        }
        return <HomePage poets={poets} onSelectPoet={handleSelectPoet} filteredPoets={filteredPoets} />;
    };

    return (
        <div className="bg-stone-50 min-h-screen" style={{ fontFamily: "'Tajawal', sans-serif" }}>
            <style>
                {`
                @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;900&display=swap');
                @keyframes fadeIn {
                    from { opacity: 0; transform: translateY(10px); }
                    to { opacity: 1; transform: translateY(0); }
                }
                .animate-fade-in { animation: fadeIn 0.5s ease-out forwards; }
                `}
            </style>
            
            <Header onSearch={setSearchQuery} searchQuery={searchQuery} />
            
            {renderContent()}

            <footer className="bg-stone-800 text-stone-300 p-6 mt-12 text-center">
                <p>&copy; 2025 ديوان الشعر العراقي. تصميم وتطوير بواسطة كرار حيدر و Gemini.</p>
                <p className="text-sm text-stone-400 mt-2">موسوعة لكل ما هو جميل في الشعر الشعبي العراقي.</p>
            </footer>
        </div>
    );
}

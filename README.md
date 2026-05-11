<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>متجر Play - نسخة محاكاة</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #ffffff;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }
        .active-tab {
            color: #01875f;
            border-bottom: 3px solid #01875f;
        }
        .app-card:active {
            background-color: #f1f3f4;
        }
        .search-bar {
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body class="pb-20">

    <div class="sticky top-0 bg-white z-50 p-3">
        <div class="flex items-center bg-gray-100 rounded-lg px-4 py-3 search-bar">
            <i class="fas fa-search text-gray-500 ml-3"></i>
            <input type="text" placeholder="البحث عن التطبيقات والألعاب" class="bg-transparent flex-1 outline-none text-sm text-right">
            <i class="fas fa-microphone text-gray-500 mr-3"></i>
            <div class="w-8 h-8 bg-purple-600 rounded-full flex items-center justify-center text-white text-xs mr-2 shadow-sm">م</div>
        </div>
        
        <div class="flex justify-around mt-4 text-gray-600 font-medium text-sm">
            <div class="pb-2 active-tab">لك</div>
            <div class="pb-2">أهم التصنيفات</div>
            <div class="pb-2">الأطفال</div>
            <div class="pb-2">العروض</div>
        </div>
    </div>

    <div class="p-4">
        <div class="flex justify-between items-center mb-4">
            <h2 class="text-lg font-bold text-gray-800">تطبيقات مقترحة لك</h2>
            <i class="fas fa-arrow-left text-gray-500"></i>
        </div>
        
        <div id="apps-list" class="space-y-4">
            </div>
    </div>

    <div class="fixed bottom-0 w-full bg-white border-t flex justify-around py-2 text-[10px] text-gray-500 z-50">
        <div class="flex flex-col items-center text-green-700">
            <i class="fas fa-gamepad text-xl mb-1"></i>
            <span>الألعاب</span>
        </div>
        <div class="flex flex-col items-center">
            <i class="fas fa-th-large text-xl mb-1 text-gray-400"></i>
            <span>التطبيقات</span>
        </div>
        <div class="flex flex-col items-center">
            <i class="fas fa-tags text-xl mb-1"></i>
            <span>العروض</span>
        </div>
        <div class="flex flex-col items-center">
            <i class="fas fa-book text-xl mb-1"></i>
            <span>الكتب</span>
        </div>
    </div>

    <script>
        const appsData = [
            { id: 1, name: "واتساب ماسنجر", developer: "WhatsApp LLC", icon: "https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg", rating: "4.3", size: "32 م.ب" },
            { id: 2, name: "فيسبوك", developer: "Meta Platforms, Inc.", icon: "https://upload.wikimedia.org/wikipedia/commons/0/05/Facebook_Logo_%282019%29.png", rating: "4.1", size: "58 م.ب" },
            { id: 3, name: "تيك توك", developer: "TikTok Pte. Ltd.", icon: "https://upload.wikimedia.org/wikipedia/en/a/a9/TikTok_logo.svg", rating: "4.5", size: "92 م.ب" },
            { id: 4, name: "إنستغرام", developer: "Instagram", icon: "https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg", rating: "4.2", size: "45 م.ب" },
            { id: 5, name: "تليجرام", developer: "Telegram FZ-LLC", icon: "https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg", rating: "4.4", size: "29 م.ب" }
        ];

        const appsList = document.getElementById('apps-list');
        appsData.forEach(app => {
            appsList.innerHTML += `
                <div class="app-card flex items-center p-1 rounded-xl transition-transform cursor-pointer">
                    <img src="${app.icon}" class="w-14 h-14 rounded-xl shadow-sm ml-4 object-cover">
                    <div class="flex-1 border-b border-gray-100 pb-3">
                        <div class="text-sm font-medium text-gray-900">${app.name}</div>
                        <div class="text-xs text-gray-500">${app.developer}</div>
                        <div class="text-[10px] text-gray-400 mt-1">${app.rating} ★ • ${app.size}</div>
                    </div>
                </div>`;
        });
    </script>
</body>
</html>

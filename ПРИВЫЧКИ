<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Система Целей - 84 Days</title>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    
    <!-- Alpine.js -->
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.13.3/dist/cdn.min.js"></script>

    <style>
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #F8FAFC; /* Мягкий серо-голубой, не слепит */
        }
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
        }
        
        .custom-scrollbar::-webkit-scrollbar {
            height: 12px;
            width: 12px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #F8FAFC;
            border-radius: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background-color: #CBD5E1;
            border-radius: 6px;
            border: 3px solid #F8FAFC;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background-color: #94A3B8;
        }

        .sticky-col-header {
            position: sticky;
            left: 0;
            z-index: 30;
            background-color: white;
            border-right: 1px solid #E5E7EB;
        }
        .sticky-col-cell {
            position: sticky;
            left: 0;
            z-index: 20;
            background-color: white;
            border-right: 1px solid #E5E7EB;
        }
        
        .check-box {
            transition: all 0.2s ease;
        }
        
        .text-gradient {
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-image: linear-gradient(to right, #2563EB, #7C3AED);
        }
        .bg-gradient-primary {
            background-image: linear-gradient(to right, #2563EB, #7C3AED);
        }

        .text-status-red { color: #ef4444; }
        .text-status-orange { color: #f97316; }
        .text-status-green { color: #22c55e; }
        .bg-status-red { background-color: #ef4444; }
        .bg-status-orange { background-color: #f97316; }
        .bg-status-green { background-color: #22c55e; }

        [x-cloak] { display: none !important; }

        /* Dark Mode - Complete Styling */
        html.dark body { background-color: #0F172A; color: #E2E8F0; }
        html.dark .bg-white { background-color: #1E293B; border-color: #334155; }
        html.dark .bg-slate-50 { background-color: #1E293B; }
        html.dark .bg-slate-50\/50 { background-color: rgba(30, 41, 59, 0.5); }
        html.dark .bg-slate-100 { background-color: #334155; }
        html.dark .bg-slate-100\/50 { background-color: rgba(51, 65, 85, 0.5); }
        html.dark .text-slate-900 { color: #F1F5F9; }
        html.dark .text-slate-800 { color: #E2E8F0; }
        html.dark .text-slate-700 { color: #CBD5E1; }
        html.dark .text-slate-600 { color: #94A3B8; }
        html.dark .text-slate-500 { color: #94A3B8; }
        html.dark .text-slate-400 { color: #64748B; }
        html.dark .border-slate-100 { border-color: #334155; }
        html.dark .border-slate-200 { border-color: #475569; }
        html.dark .border-slate-300 { border-color: #64748B; }
        html.dark .shadow-sm { box-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.4); }
        html.dark .shadow-md { box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.4); }
        html.dark input { color: #F1F5F9; background: transparent; }
        html.dark input::placeholder { color: #64748B; }
        html.dark .sticky-col-header, html.dark .sticky-col-cell { background-color: #1E293B; border-right-color: #475569; }
        html.dark td, html.dark th { border-color: #475569; }
        html.dark .divide-slate-100 > :not([hidden]) ~ :not([hidden]) { border-color: #475569; }
        html.dark .hover\:bg-slate-50:hover { background-color: #334155; }
        html.dark .hover\:bg-slate-50\/50:hover { background-color: rgba(51, 65, 85, 0.5); }
        html.dark .hover\:bg-slate-100\/80:hover { background-color: rgba(51, 65, 85, 0.8); }
        html.dark .group-hover\:bg-slate-50 { background-color: #334155; }
        
        /* Dark mode checkbox fix */
        html.dark .check-box, html.dark button div[class*="rounded-md"], html.dark button div[class*="rounded-xl"] {
            border-color: #64748B;
        }
        html.dark .border-slate-300 { border-color: #64748B; }
        
        /* Dark mode scrollbar */
        html.dark .custom-scrollbar::-webkit-scrollbar-track { background: #1E293B; }
        html.dark .custom-scrollbar::-webkit-scrollbar-thumb { background-color: #475569; border-color: #1E293B; }
        html.dark .custom-scrollbar::-webkit-scrollbar-thumb:hover { background-color: #64748B; }
        
        /* Dark mode emoji picker */
        html.dark .emoji-grid button:hover { background: #334155; }

        /* Celebration Particles */
        .particle {
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            font-size: 20px;
            animation: particleFly var(--duration) ease-out forwards;
        }
        @keyframes particleFly {
            0% {
                opacity: 1;
                transform: translate(0, 0) rotate(0deg) scale(1);
            }
            100% {
                opacity: 0;
                transform: translate(var(--tx), var(--ty)) rotate(var(--rot)) scale(0.2);
            }
        }

        /* Checkbox pop animation */
        @keyframes checkPop {
            0% { transform: scale(1); }
            30% { transform: scale(1.4); }
            60% { transform: scale(0.9); }
            100% { transform: scale(1); }
        }
        .check-pop {
            animation: checkPop 0.4s cubic-bezier(0.36, 1.5, 0.6, 1) forwards;
        }

        /* Ripple effect */
        @keyframes ripple {
            0% { transform: scale(0); opacity: 0.6; }
            100% { transform: scale(4); opacity: 0; }
        }
        .ripple-ring {
            position: absolute;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            pointer-events: none;
            animation: ripple 0.6s ease-out forwards;
        }

        /* Glow pulse on full day */
        @keyframes glowPulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(34, 197, 94, 0); }
            50% { box-shadow: 0 0 20px 8px rgba(34, 197, 94, 0.3); }
        }

        /* Emoji picker popup */
        .emoji-grid {
            display: grid;
            grid-template-columns: repeat(8, 1fr);
            gap: 2px;
            max-height: 200px;
            overflow-y: auto;
        }
        .emoji-grid button {
            font-size: 22px;
            padding: 4px;
            border-radius: 6px;
            transition: all 0.15s;
            cursor: pointer;
            border: none;
            background: transparent;
        }
        .emoji-grid button:hover {
            background: #E2E8F0;
            transform: scale(1.2);
        }
    </style>
</head>
<body class="text-slate-800 antialiased min-h-screen pb-20" x-data="app()" x-init="initApp()">

    <!-- Particle Container -->
    <div id="particleContainer"></div>

    <!-- Floating Menu -->
    <div x-data="{ menuOpen: false }" class="fixed top-6 left-6 z-50">
        <button @click="menuOpen = !menuOpen" class="p-3 bg-white dark:bg-slate-800 rounded-2xl shadow-lg border border-slate-200 dark:border-slate-700 text-slate-600 dark:text-slate-300 hover:bg-slate-50 dark:hover:bg-slate-700 transition-colors focus:outline-none group">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 transition-transform duration-300" :class="menuOpen ? 'rotate-90' : ''" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
        </button>

        <div x-show="menuOpen" 
             @click.outside="menuOpen = false" 
             x-transition:enter="transition ease-out duration-200"
             x-transition:enter-start="opacity-0 -translate-y-2"
             x-transition:enter-end="opacity-100 translate-y-0"
             x-transition:leave="transition ease-in duration-150"
             x-transition:leave-start="opacity-100 translate-y-0"
             x-transition:leave-end="opacity-0 -translate-y-2"
             class="absolute top-full left-0 mt-3 bg-white dark:bg-slate-800 rounded-2xl shadow-xl border border-slate-200 dark:border-slate-700 p-3 flex flex-col gap-3 min-w-[140px]">
            
            <div class="flex items-center gap-2">
                <button @click="setTheme('light')" 
                        class="flex-1 p-2 rounded-xl border flex items-center justify-center transition-all"
                        :class="!isDark ? 'bg-orange-50 border-orange-200 text-orange-500 shadow-sm' : 'bg-transparent border-transparent text-slate-400 hover:bg-slate-100 dark:hover:bg-slate-700'">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
                    </svg>
                </button>
                <button @click="setTheme('dark')" 
                        class="flex-1 p-2 rounded-xl border flex items-center justify-center transition-all"
                        :class="isDark ? 'bg-blue-900/30 border-blue-800 text-blue-400 shadow-sm' : 'bg-transparent border-transparent text-slate-400 hover:bg-slate-100 dark:hover:bg-slate-700'">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
                    </svg>
                </button>
            </div>

            <div class="w-full h-px bg-slate-100 dark:bg-slate-700"></div>

            <div class="flex flex-col gap-2">
                <span class="text-[10px] font-bold text-slate-400 uppercase tracking-widest text-center">Интерфейс</span>
                <div class="flex gap-2">
                    <button @click="setInterface(1)" 
                            class="flex-1 py-1.5 text-xs font-bold rounded-lg border transition-all"
                            :class="interfaceMode === 1 ? 'bg-slate-800 text-white border-slate-800 dark:bg-white dark:text-slate-900' : 'bg-transparent border-slate-200 dark:border-slate-600 text-slate-500 hover:border-slate-400'">
                        V1
                    </button>
                    <button @click="setInterface(2)" 
                            class="flex-1 py-1.5 text-xs font-bold rounded-lg border transition-all"
                            :class="interfaceMode === 2 ? 'bg-slate-800 text-white border-slate-800 dark:bg-white dark:text-slate-900' : 'bg-transparent border-slate-200 dark:border-slate-600 text-slate-500 hover:border-slate-400'">
                        V2
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Header Section -->
    <header class="max-w-screen-2xl mx-auto px-4 pt-8 pb-6">
        <div class="flex flex-col md:flex-row justify-between items-start md:items-end gap-6 mb-8">
            <div>
                <h1 class="text-4xl md:text-5xl font-extrabold tracking-tight text-slate-900 uppercase mb-2">
                    СИСТЕМА ЦЕЛЕЙ
                </h1>
                <div class="h-1.5 w-full md:w-64 bg-gradient-primary rounded-full"></div>
            </div>
            
            <div class="flex items-center gap-2 text-sm font-medium text-slate-500 bg-white px-4 py-2 rounded-full shadow-sm border border-slate-100">
                <span class="relative flex h-2.5 w-2.5">
                  <span x-show="isSyncing" class="animate-ping absolute inline-flex h-full w-full rounded-full bg-blue-400 opacity-75"></span>
                  <span :class="isSyncing ? 'bg-blue-500' : 'bg-green-500'" class="relative inline-flex rounded-full h-2.5 w-2.5"></span>
                </span>
                <span x-text="isSyncing ? 'Сохраняю...' : 'Автосохранение: ● Активно'"></span>
            </div>
        </div>

        <!-- Hero Card -->
        <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 md:p-8 flex flex-col md:flex-row justify-between items-center gap-8">
            <div class="flex-1 w-full flex flex-col items-center text-center">
                <div class="flex items-baseline gap-2 mb-1 justify-center">
                    <span class="text-base font-bold text-slate-500 uppercase tracking-wider">Окончание:</span>
                    <span class="text-xl font-bold text-slate-700" x-text="endDateDisplay"></span>
                </div>
                
                <div class="flex items-baseline gap-3 justify-center">
                    <span class="text-7xl md:text-8xl font-black text-slate-900 leading-none tracking-tighter" x-text="daysRemaining"></span>
                    <span class="text-5xl md:text-6xl font-bold text-blue-500">Дней</span>
                </div>
                
                <div class="mt-4">
                    <span class="inline-flex items-center px-4 py-1.5 rounded-full bg-slate-100 text-slate-600 text-sm font-semibold border border-slate-200" x-text="weeksRemainingText"></span>
                </div>
            </div>

            <div class="hidden md:block w-px h-32 bg-gradient-to-b from-slate-100 via-slate-200 to-slate-100"></div>
            
            <div class="text-right hidden md:block">
                <div class="text-sm text-slate-400 mb-1">Сегодня</div>
                <div class="text-xl font-bold text-slate-800 capitalize" x-text="todayDisplay"></div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="max-w-screen-2xl mx-auto px-4 space-y-12">
        
        <!-- Main Tracker -->
        <section x-data="tracker('main', 'marathon_data_v84_main_v7', [
            { name: '8:00 | 23:00', icon: '☀️', icon2: '🌙', isThreeState: true, subtitle: 'Сон' },
            { name: 'Спорт', icon: '🏋️', icon2: '', isThreeState: false },
            { name: 'Работа', icon: '💼', icon2: '', isThreeState: false },
            { name: 'Обучение', icon: '🎓', icon2: '', isThreeState: false }
        ])" class="bg-white rounded-xl shadow-md border border-slate-200 overflow-hidden">
            
            <!-- Tracker Header -->
            <div class="p-5 border-b border-slate-200 flex flex-wrap justify-between items-center gap-4 bg-white sticky top-0 z-40">
                <div class="flex items-center gap-3">
                    <div class="w-2 h-8 rounded-full bg-blue-600"></div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Трекер</h2>
                        <div class="text-sm text-slate-500 font-medium" x-text="dateRangeDisplay"></div>
                    </div>
                </div>
                
                <div class="flex flex-col items-end">
                    <div class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-1">Эффективность (Общая)</div>
                    <div class="text-3xl font-black transition-colors duration-300 font-mono"
                         :style="`color: ${getColor(totalProgress)}`">
                        <span x-text="totalProgress.toFixed(2)"></span>%
                    </div>
                </div>
            </div>

            <!-- ============================================ -->
            <!-- V1: TABLE VIEW -->
            <!-- ============================================ -->
            <div x-show="interfaceMode === 1" class="relative overflow-x-auto custom-scrollbar" style="max-height: 80vh;">
                <table class="w-full border-collapse">
                    <thead class="bg-white sticky top-0 z-30 shadow-sm">
                        <tr>
                            <th class="sticky-col-header min-w-[280px] p-3 text-left border-b border-slate-200 bg-white">
                                <span class="text-xs font-bold text-slate-400 uppercase">Задача / Привычка</span>
                            </th>
                            <template x-for="(week, weekIndex) in weeks" :key="weekIndex">
                                <th :colspan="week.days.length" class="text-center py-2 px-1 border-l border-b border-slate-200 bg-white">
                                    <span class="text-[10px] font-bold text-slate-500 uppercase tracking-wider" x-text="`${weekIndex + 1} НЕД`"></span>
                                </th>
                            </template>
                            <th rowspan="2" class="min-w-[60px] p-2 border-b border-l border-slate-200 bg-white z-30 text-center">
                                <span class="text-[10px] font-bold text-slate-400 vertical-rl">ИТОГ</span>
                            </th>
                        </tr>
                        <tr>
                            <th class="sticky-col-header p-2 border-b border-slate-200 bg-white"></th>
                            <template x-for="(day, dayIndex) in days" :key="dayIndex">
                                <th class="min-w-[42px] w-[42px] p-1 border-l border-b border-slate-200 text-center transition-colors"
                                    :class="isToday(day.date) ? 'bg-blue-50' : 'bg-white'">
                                    <div class="flex flex-col items-center">
                                        <span class="text-[10px] font-medium text-slate-400 uppercase mb-0.5" x-text="day.weekdayShort"></span>
                                        <span class="text-xs font-bold" :class="isToday(day.date) ? 'text-blue-600' : 'text-slate-700'" x-text="day.dayNum"></span>
                                    </div>
                                </th>
                            </template>
                        </tr>
                    </thead>
                    
                    <tbody class="divide-y divide-slate-100">
                        <template x-for="(habit, hIndex) in habits" :key="habit.id">
                            <tr class="group hover:bg-slate-50/50 transition-colors">
                                <td class="sticky-col-cell p-3 group-hover:bg-slate-50 transition-colors relative">
                                    <div class="flex items-center gap-3 pl-2">
                                        <span class="text-xs font-bold w-4 text-center" 
                                              :class="hIndex < 4 ? 'text-slate-500' : 'text-slate-300'" 
                                              x-text="hIndex + 1"></span>
                                        <div class="flex-1 relative">
                                            <div class="flex items-center gap-2 mb-0.5">
                                                <input type="text" x-model="habit.name" @input.debounce.500ms="saveData" 
                                                       class="w-full bg-transparent border-none p-0 text-sm placeholder-slate-400 focus:ring-0 focus:text-blue-600 transition-all"
                                                       :class="hIndex < 4 ? 'font-bold text-slate-900' : 'font-medium text-slate-600'"
                                                       placeholder="Название привычки">
                                                <!-- Emoji Buttons -->
                                                <button @click="openEmojiPicker(hIndex, 1, $event)" class="text-2xl hover:scale-125 transition-transform cursor-pointer flex-shrink-0" x-text="habit.icon" title="Сменить эмодзи 1"></button>
                                                <button x-show="habit.icon2" @click="openEmojiPicker(hIndex, 2, $event)" class="text-2xl hover:scale-125 transition-transform cursor-pointer flex-shrink-0" x-text="habit.icon2" title="Сменить эмодзи 2"></button>
                                            </div>
                                            <!-- Subtitle for habit (e.g., "Сон") -->
                                            <div x-show="habit.subtitle" class="text-[10px] text-slate-400 font-medium uppercase tracking-wider" x-text="habit.subtitle"></div>
                                            <div class="flex items-center gap-2 opacity-0 group-hover:opacity-100 transition-opacity">
                                                 <button @click="deleteHabit(hIndex)" class="text-slate-300 hover:text-red-500 transition-colors" title="Удалить">
                                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                                                    </svg>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </td>
                                
                                <template x-for="(day, dIndex) in days" :key="dIndex">
                                    <td class="border-l border-slate-100 p-0 text-center h-12 relative" 
                                        :class="isToday(day.date) ? 'bg-blue-50/30' : ''">
                                        <button @click="toggleCheckWithCelebration(hIndex, dIndex, $event)" 
                                                class="w-full h-full flex items-center justify-center focus:outline-none focus:bg-slate-100/50"
                                                :title="`${habit.name} - ${day.dateString}`">
                                            
                                            <div class="w-6 h-6 rounded-md transition-all duration-200 flex items-center justify-center overflow-hidden"
                                                 :class="{
                                                     'border-2 border-slate-300 dark:border-slate-500': hIndex < 4 && getCheckValue(hIndex, dIndex) === 0,
                                                     'border border-slate-200 dark:border-slate-600': hIndex >= 4 && getCheckValue(hIndex, dIndex) === 0,
                                                     'border': getCheckValue(hIndex, dIndex) > 0 && getCheckValue(hIndex, dIndex) < 1,
                                                     'bg-white shadow-sm hover:border-blue-300': getCheckValue(hIndex, dIndex) === 0,
                                                     'shadow-md': getCheckValue(hIndex, dIndex) > 0,
                                                     'border-transparent': getCheckValue(hIndex, dIndex) === 1
                                                 }"
                                                 :style="{
                                                     'border-color': getCheckValue(hIndex, dIndex) > 0 ? getColor(getDayProgress(dIndex)) : '',
                                                     'background-color': getCheckValue(hIndex, dIndex) === 1 ? getColor(getDayProgress(dIndex)) : ''
                                                 }">
                                                
                                                <svg x-show="getCheckValue(hIndex, dIndex) === 1" xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-white" viewBox="0 0 20 20" fill="currentColor">
                                                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                                                </svg>

                                                <div x-show="getCheckValue(hIndex, dIndex) === 0.5" class="w-full h-full relative">
                                                    <div class="absolute bottom-0 left-0 right-0 h-1/2" :style="`background-color: ${getColor(getDayProgress(dIndex))}`"></div>
                                                </div>
                                            </div>
                                        </button>
                                    </td>
                                </template>

                                <td class="border-l border-slate-200 bg-white"></td>
                            </tr>
                        </template>
                    </tbody>
                    
                    <tfoot class="bg-white border-t border-slate-200">
                        <tr>
                            <td class="sticky-col-cell p-3 text-right">
                                <span class="text-xs font-bold text-slate-400 uppercase">Итог дня</span>
                            </td>
                            <template x-for="(day, dIndex) in days" :key="dIndex">
                                <td class="border-l border-slate-200 p-2 align-bottom h-24" :class="isToday(day.date) ? 'bg-blue-50' : ''">
                                    <div class="flex flex-col items-center justify-end h-full w-full gap-1">
                                        <div class="relative w-2 bg-slate-200 rounded-full overflow-hidden" style="height: 60px;">
                                            <div class="absolute bottom-0 left-0 w-full rounded-full transition-all duration-500"
                                                 :style="`height: ${getDayProgress(dIndex)}%; background-color: ${getColor(getDayProgress(dIndex))}`"></div>
                                        </div>
                                        <span class="text-[9px] font-bold" 
                                              :style="`color: ${getColor(getDayProgress(dIndex))}`"
                                              x-text="Math.round(getDayProgress(dIndex)) + '%'"></span>
                                    </div>
                                </td>
                            </template>
                            <td class="p-2 border-l border-slate-200 text-center"></td>
                        </tr>
                    </tfoot>
                </table>
            </div>

            <!-- V1 Add Habit Button -->
            <div x-show="interfaceMode === 1" class="p-4 border-t border-slate-200 bg-white flex items-center justify-between">
                <button @click="addHabit()" class="flex items-center gap-2 px-4 py-2 bg-white border border-slate-300 rounded-lg shadow-sm hover:bg-slate-50 hover:border-blue-400 transition-all group">
                    <div class="w-5 h-5 rounded-full bg-blue-100 text-blue-600 flex items-center justify-center group-hover:bg-blue-600 group-hover:text-white transition-colors">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-3 w-3" viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M10 3a1 1 0 011 1v5h5a1 1 0 110 2h-5v5a1 1 0 11-2 0v-5H4a1 1 0 110-2h5V4a1 1 0 011-1z" clip-rule="evenodd" />
                        </svg>
                    </div>
                    <span class="text-sm font-semibold text-slate-600 group-hover:text-slate-900">Добавить привычку</span>
                </button>
                <span class="text-xs text-slate-400">Начало: 17 фев. 2026 · Окончание: 12 мая 2026</span>
            </div>

            <!-- ============================================ -->
            <!-- V2: DAILY CARD VIEW -->
            <!-- ============================================ -->
            <div x-show="interfaceMode === 2" x-cloak class="flex flex-col items-center">

                <!-- Progress Bar -->
                <div class="w-full px-6 pt-5 pb-3">
                    <div class="max-w-lg mx-auto bg-white p-4 rounded-2xl border border-slate-200">
                        <div class="flex justify-between items-end mb-2">
                            <span class="text-sm font-medium text-slate-500">Общий прогресс</span>
                            <span class="text-xl font-bold font-mono transition-colors duration-300"
                                  :style="`color: ${getColor(totalProgress)}`"
                                  x-text="totalProgress.toFixed(2) + '%'"></span>
                        </div>
                        <div class="h-3 w-full bg-slate-100 rounded-full overflow-hidden">
                            <div class="h-full rounded-full transition-all duration-700 ease-out"
                                 :style="`width: ${Math.min(totalProgress, 100)}%; background-color: ${getColor(totalProgress)}`"></div>
                        </div>
                        <p class="text-xs text-slate-400 text-right mt-1">От общей цели 84 дней</p>
                    </div>
                </div>

                <!-- Date Navigation -->
                <div class="w-full px-6 py-3">
                    <div class="max-w-lg mx-auto flex items-center justify-between bg-white p-4 rounded-2xl border border-slate-200">
                        <button @click="v2PrevDay()" class="p-3 hover:bg-slate-50 rounded-xl transition-colors text-slate-400 hover:text-slate-700 active:scale-95">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>
                        </button>
                        
                        <div class="flex flex-col items-center">
                            <div class="text-lg font-bold text-slate-800" x-text="v2DateTitle()"></div>
                            <div class="text-sm font-semibold transition-colors duration-300"
                                 :style="`color: ${getColor(getDayProgress(v2DayIndex))}`"
                                 x-text="'Эффективность: ' + Math.round(getDayProgress(v2DayIndex)) + '%'">
                            </div>
                        </div>

                        <button @click="v2NextDay()" class="p-3 hover:bg-slate-50 rounded-xl transition-colors text-slate-400 hover:text-slate-700 active:scale-95">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>
                        </button>
                    </div>
                </div>

                <!-- Habits List -->
                <div class="w-full px-6 py-3 pb-6">
                    <div class="max-w-lg mx-auto space-y-3">
                        <template x-for="(habit, hIndex) in habits" :key="habit.id">
                            <div class="flex items-center justify-between bg-white hover:bg-slate-50 p-4 rounded-xl border-l-4 border border-slate-200 hover:border-slate-300 transition-all group"
                                 :style="`border-left-color: ${habit.color || '#3b82f6'}`">
                                
                                <div class="flex items-center gap-3 flex-1 min-w-0">
                                    <!-- Settings Button -->
                                    <button @click="openHabitSettings(hIndex)" 
                                            class="w-8 h-8 flex-shrink-0 rounded-lg flex items-center justify-center text-white shadow-md hover:scale-110 transition-transform active:scale-95"
                                            :style="`background-color: ${habit.color || '#3b82f6'}`">
                                        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                                        </svg>
                                    </button>
                                    
                                    <div class="flex-1 min-w-0">
                                        <div class="flex items-center gap-2">
                                            <!-- Editable Name -->
                                            <input type="text" x-model="habit.name" @input.debounce.500ms="saveData"
                                                   class="bg-transparent border-none p-0 focus:ring-0 transition-colors truncate w-full"
                                                   :class="hIndex < 4 ? 'font-bold text-slate-900 text-base' : 'font-medium text-slate-700 text-sm'"
                                                   placeholder="Название привычки">
                                            <!-- Emoji Buttons -->
                                            <button @click="openEmojiPicker(hIndex, 1, $event)" class="text-2xl flex-shrink-0 hover:scale-125 transition-transform cursor-pointer" x-text="habit.icon" title="Сменить эмодзи 1"></button>
                                            <button x-show="habit.icon2" @click="openEmojiPicker(hIndex, 2, $event)" class="text-2xl flex-shrink-0 hover:scale-125 transition-transform cursor-pointer" x-text="habit.icon2" title="Сменить эмодзи 2"></button>
                                        </div>
                                        <!-- Time & Days Info -->
                                        <div class="flex items-center gap-2 mt-1 flex-wrap">
                                            <span x-show="habit.time" class="text-xs font-semibold px-2 py-0.5 rounded-full bg-slate-100 text-slate-600"
                                                  x-text="'⏰ ' + habit.time"></span>
                                            <span x-show="habit.repeatDays && habit.repeatDays.length < 7 && habit.repeatDays.length > 0" 
                                                  class="text-xs font-semibold px-2 py-0.5 rounded-full bg-blue-50 text-blue-600"
                                                  x-text="'📅 ' + habit.repeatDays.map(d => dayNames[d]).join(', ')"></span>
                                            <span x-show="habit.subtitle" class="text-[10px] text-slate-400 font-semibold uppercase tracking-wider" x-text="habit.subtitle"></span>
                                        </div>
                                    </div>
                                </div>

                                <button @click="toggleCheckWithCelebration(hIndex, v2DayIndex, $event)" 
                                        class="relative w-12 h-12 flex-shrink-0 focus:outline-none transition-transform active:scale-90 ml-3">
                                    
                                    <div class="w-full h-full rounded-xl border-2 transition-all duration-200 flex items-center justify-center overflow-hidden"
                                         :class="{
                                             'bg-white border-slate-300 hover:border-slate-400': getCheckValue(hIndex, v2DayIndex) === 0,
                                             'border-transparent shadow-lg': getCheckValue(hIndex, v2DayIndex) === 1
                                         }"
                                         :style="{
                                             'background-color': getCheckValue(hIndex, v2DayIndex) === 1 ? (habit.color || getColor(getDayProgress(v2DayIndex))) : '',
                                             'border-color': getCheckValue(hIndex, v2DayIndex) === 0.5 ? (habit.color || getColor(getDayProgress(v2DayIndex))) : ''
                                         }">
                                        
                                        <!-- Full check -->
                                        <svg x-show="getCheckValue(hIndex, v2DayIndex) === 1" xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-white" viewBox="0 0 20 20" fill="currentColor">
                                            <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                                        </svg>

                                        <!-- Half state -->
                                        <template x-if="getCheckValue(hIndex, v2DayIndex) === 0.5">
                                            <div class="w-full h-full relative">
                                                <div class="absolute bottom-0 left-0 right-0 h-1/2 rounded-b-lg transition-colors duration-300"
                                                     :style="`background-color: ${habit.color || getColor(getDayProgress(v2DayIndex))}`"></div>
                                            </div>
                                        </template>
                                    </div>
                                </button>
                            </div>
                        </template>
                        
                        <!-- Add Habit -->
                        <button @click="addHabit()" class="w-full py-4 border-2 border-dashed border-slate-200 rounded-xl text-slate-400 hover:border-blue-300 hover:text-blue-500 hover:bg-blue-50/30 transition-all font-medium text-sm flex items-center justify-center gap-2 active:scale-[0.98]">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M10 3a1 1 0 011 1v5h5a1 1 0 110 2h-5v5a1 1 0 11-2 0v-5H4a1 1 0 110-2h5V4a1 1 0 011-1z" clip-rule="evenodd" />
                            </svg>
                            Добавить привычку
                        </button>

                        <div class="text-center text-xs text-slate-400 font-medium pt-3 pb-2">
                            День <span class="font-bold text-slate-500" x-text="v2DayIndex + 1"></span> из 84
                        </div>
                    </div>
                </div>
            </div>

            <!-- Emoji Picker Popup -->
            <div x-show="emojiPickerOpen" x-cloak
                 @click.outside="emojiPickerOpen = false"
                 x-transition:enter="transition ease-out duration-150"
                 x-transition:enter-start="opacity-0 scale-90"
                 x-transition:enter-end="opacity-100 scale-100"
                 x-transition:leave="transition ease-in duration-100"
                 x-transition:leave-start="opacity-100 scale-100"
                 x-transition:leave-end="opacity-0 scale-90"
                 class="fixed z-[60] bg-white rounded-2xl shadow-2xl border border-slate-200 p-4 w-[320px]"
                 :style="`top: ${emojiPickerY}px; left: ${emojiPickerX}px;`">
                <div class="text-xs font-bold text-slate-400 uppercase mb-2 tracking-wider">Выбери эмодзи</div>
                <div class="emoji-grid">
                    <template x-for="emoji in emojiList" :key="emoji">
                        <button @click="setHabitEmoji(emoji)" x-text="emoji"></button>
                    </template>
                </div>
            </div>

            <!-- Habit Settings Modal -->
            <div x-show="habitSettingsOpen" x-cloak
                 class="fixed inset-0 z-[70] flex items-center justify-center p-4"
                 x-transition:enter="transition ease-out duration-200"
                 x-transition:enter-start="opacity-0"
                 x-transition:enter-end="opacity-100"
                 x-transition:leave="transition ease-in duration-150"
                 x-transition:leave-start="opacity-100"
                 x-transition:leave-end="opacity-0">
                
                <!-- Backdrop -->
                <div class="absolute inset-0 bg-black/40" @click="closeHabitSettings()"></div>
                
                <!-- Modal Content -->
                <div class="relative bg-white dark:bg-slate-800 rounded-3xl shadow-2xl w-full max-w-md p-6 space-y-5"
                     x-transition:enter="transition ease-out duration-200"
                     x-transition:enter-start="opacity-0 scale-90 translate-y-4"
                     x-transition:enter-end="opacity-100 scale-100 translate-y-0">
                    
                    <!-- Header -->
                    <div class="flex items-center justify-between">
                        <h3 class="text-xl font-bold text-slate-800 dark:text-white">Настройки привычки</h3>
                        <button @click="closeHabitSettings()" class="p-2 hover:bg-slate-100 dark:hover:bg-slate-700 rounded-xl transition-colors">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-slate-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                            </svg>
                        </button>
                    </div>

                    <template x-if="getHabitSettings()">
                        <div class="space-y-5">
                            <!-- Color Selection -->
                            <div>
                                <label class="text-sm font-semibold text-slate-600 dark:text-slate-300 mb-2 block">🎨 Цвет привычки</label>
                                <div class="flex flex-wrap gap-2">
                                    <template x-for="color in colorPalette" :key="color">
                                        <button @click="setHabitColor(color)" 
                                                class="w-8 h-8 rounded-lg border-2 transition-all hover:scale-110 active:scale-95"
                                                :class="getHabitSettings().color === color ? 'border-slate-800 dark:border-white scale-110 shadow-lg' : 'border-transparent'"
                                                :style="`background-color: ${color}`">
                                        </button>
                                    </template>
                                </div>
                            </div>

                            <!-- Time Selection -->
                            <div>
                                <label class="text-sm font-semibold text-slate-600 dark:text-slate-300 mb-2 block">⏰ Время выполнения</label>
                                <input type="time" 
                                       x-model="habits[habitSettingsIndex].time" 
                                       @input="saveData()"
                                       class="w-full px-4 py-3 bg-slate-50 dark:bg-slate-700 border border-slate-200 dark:border-slate-600 rounded-xl text-slate-800 dark:text-white font-medium focus:outline-none focus:ring-2 focus:ring-blue-500">
                            </div>

                            <!-- Repeat Days -->
                            <div>
                                <label class="text-sm font-semibold text-slate-600 dark:text-slate-300 mb-2 block">📅 Повторять в дни</label>
                                <div class="flex gap-2">
                                    <template x-for="(dayName, idx) in dayNames" :key="idx">
                                        <button @click="toggleRepeatDay(idx)"
                                                class="flex-1 py-2 px-1 rounded-lg text-xs font-bold transition-all active:scale-95"
                                                :class="getHabitSettings().repeatDays.includes(idx) 
                                                    ? 'bg-blue-500 text-white shadow-md' 
                                                    : 'bg-slate-100 dark:bg-slate-700 text-slate-400 hover:bg-slate-200 dark:hover:bg-slate-600'"
                                                x-text="dayName">
                                        </button>
                                    </template>
                                </div>
                                <p class="text-xs text-slate-400 mt-2">Оставь все выбранные для ежедневной привычки</p>
                            </div>

                            <!-- Delete Habit -->
                            <div class="pt-3 border-t border-slate-200 dark:border-slate-700">
                                <button @click="deleteHabit(habitSettingsIndex); closeHabitSettings();" 
                                        class="w-full py-3 bg-red-50 dark:bg-red-900/30 text-red-600 dark:text-red-400 rounded-xl font-semibold hover:bg-red-100 dark:hover:bg-red-900/50 transition-colors flex items-center justify-center gap-2">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                                    </svg>
                                    Удалить привычку
                                </button>
                            </div>
                        </div>
                    </template>
                </div>
            </div>

        </section>

    </main>

    <script>
        // ============================
        // CELEBRATION SYSTEM
        // ============================
        const CelebrationEngine = {
            audioCtx: null,
            
            getAudioCtx() {
                if (!this.audioCtx) {
                    this.audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                }
                return this.audioCtx;
            },

            // Different celebration sound types
            playCheckSound() {
                try {
                    const ctx = this.getAudioCtx();
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    osc.connect(gain);
                    gain.connect(ctx.destination);
                    osc.frequency.setValueAtTime(880, ctx.currentTime);
                    osc.frequency.exponentialRampToValueAtTime(1320, ctx.currentTime + 0.08);
                    osc.type = 'sine';
                    gain.gain.setValueAtTime(0.15, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.25);
                    osc.start(ctx.currentTime);
                    osc.stop(ctx.currentTime + 0.25);
                } catch(e) {}
            },

            playHalfCheckSound() {
                try {
                    const ctx = this.getAudioCtx();
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    osc.connect(gain);
                    gain.connect(ctx.destination);
                    osc.frequency.setValueAtTime(600, ctx.currentTime);
                    osc.frequency.exponentialRampToValueAtTime(800, ctx.currentTime + 0.1);
                    osc.type = 'triangle';
                    gain.gain.setValueAtTime(0.12, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.2);
                    osc.start(ctx.currentTime);
                    osc.stop(ctx.currentTime + 0.2);
                } catch(e) {}
            },

            playUncheckSound() {
                try {
                    const ctx = this.getAudioCtx();
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    osc.connect(gain);
                    gain.connect(ctx.destination);
                    osc.frequency.setValueAtTime(400, ctx.currentTime);
                    osc.frequency.exponentialRampToValueAtTime(200, ctx.currentTime + 0.12);
                    osc.type = 'sine';
                    gain.gain.setValueAtTime(0.08, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.15);
                    osc.start(ctx.currentTime);
                    osc.stop(ctx.currentTime + 0.15);
                } catch(e) {}
            },

            playFullDayFanfare() {
                try {
                    const ctx = this.getAudioCtx();
                    const notes = [523, 659, 784, 1047];
                    notes.forEach((freq, i) => {
                        const osc = ctx.createOscillator();
                        const gain = ctx.createGain();
                        osc.connect(gain);
                        gain.connect(ctx.destination);
                        osc.frequency.setValueAtTime(freq, ctx.currentTime + i * 0.12);
                        osc.type = 'sine';
                        gain.gain.setValueAtTime(0, ctx.currentTime + i * 0.12);
                        gain.gain.linearRampToValueAtTime(0.15, ctx.currentTime + i * 0.12 + 0.02);
                        gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + i * 0.12 + 0.35);
                        osc.start(ctx.currentTime + i * 0.12);
                        osc.stop(ctx.currentTime + i * 0.12 + 0.35);
                    });
                } catch(e) {}
            },

            playCoinSound() {
                try {
                    const ctx = this.getAudioCtx();
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    osc.connect(gain);
                    gain.connect(ctx.destination);
                    osc.frequency.setValueAtTime(988, ctx.currentTime);
                    osc.frequency.setValueAtTime(1319, ctx.currentTime + 0.08);
                    osc.type = 'square';
                    gain.gain.setValueAtTime(0.08, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.3);
                    osc.start(ctx.currentTime);
                    osc.stop(ctx.currentTime + 0.3);
                } catch(e) {}
            },

            // Particle effects
            spawnParticles(x, y, type) {
                const container = document.getElementById('particleContainer');
                const particleSets = {
                    confetti: ['🎉', '🎊', '✨', '💫', '⭐', '🌟', '🔥', '💥', '🎯', '👏'],
                    coins: ['🪙', '💰', '💎', '✨', '🏆', '🥇', '💫', '⭐'],
                    stars: ['⭐', '🌟', '✨', '💫', '🌠', '☀️', '🌈', '🎆'],
                    hearts: ['❤️', '🧡', '💛', '💚', '💙', '💜', '💖', '💗'],
                    fire: ['🔥', '💥', '⚡', '✨', '💫', '🌟', '🎇', '🎆']
                };
                
                const types = Object.keys(particleSets);
                const selectedType = type || types[Math.floor(Math.random() * types.length)];
                const particles = particleSets[selectedType];
                const count = selectedType === 'confetti' ? 18 : 12;
                
                for (let i = 0; i < count; i++) {
                    const el = document.createElement('span');
                    el.className = 'particle';
                    el.textContent = particles[Math.floor(Math.random() * particles.length)];
                    
                    const angle = (Math.random() * 360) * (Math.PI / 180);
                    const distance = 60 + Math.random() * 140;
                    const tx = Math.cos(angle) * distance;
                    const ty = Math.sin(angle) * distance - 40;
                    const rot = (Math.random() - 0.5) * 720;
                    const duration = 0.6 + Math.random() * 0.8;
                    
                    el.style.left = x + 'px';
                    el.style.top = y + 'px';
                    el.style.setProperty('--tx', tx + 'px');
                    el.style.setProperty('--ty', ty + 'px');
                    el.style.setProperty('--rot', rot + 'deg');
                    el.style.setProperty('--duration', duration + 's');
                    el.style.fontSize = (14 + Math.random() * 16) + 'px';
                    
                    container.appendChild(el);
                    
                    setTimeout(() => el.remove(), duration * 1000 + 100);
                }
            },

            spawnRipple(x, y, color) {
                const container = document.getElementById('particleContainer');
                const ring = document.createElement('div');
                ring.className = 'ripple-ring';
                ring.style.left = (x - 15) + 'px';
                ring.style.top = (y - 15) + 'px';
                ring.style.border = `3px solid ${color}`;
                container.appendChild(ring);
                setTimeout(() => ring.remove(), 700);
            },

            // Big celebration for 100% day
            bigCelebration(x, y) {
                this.playFullDayFanfare();
                
                setTimeout(() => this.spawnParticles(x, y, 'confetti'), 0);
                setTimeout(() => this.spawnParticles(x, y, 'stars'), 200);
                setTimeout(() => this.spawnParticles(x, y, 'fire'), 400);
                
                for (let i = 0; i < 3; i++) {
                    setTimeout(() => {
                        this.spawnRipple(x, y, ['#22c55e', '#3b82f6', '#a855f7'][i]);
                    }, i * 150);
                }
            }
        };

        // ============================
        // EMOJI LIST
        // ============================
        const EMOJI_LIST = [
            '☀️','🌙','🏋️','💼','🎓','📚','💪','🏃','🧘','🚴',
            '⚽','🎯','🔥','⭐','💎','🏆','🥇','🎉','❤️','🧠',
            '💡','🎨','🎵','🎮','🍎','🥦','💧','🌿','🧹','💤',
            '📝','💻','📱','📖','✍️','🗣️','🤝','👨‍💻','🏠','🚀',
            '⏰','🧪','🔬','📊','💵','🪙','🎭','🎬','📸','🌍',
            '🐶','🐱','🌸','🌊','⛰️','🏖️','✈️','🚗','🎸','🥁',
            '🍳','🧘‍♂️','🏊','🎿','⛷️','🛹','🤸','🧗','🎪','🎠',
            '🔹','🔷','🔶','🟢','🟡','🔴','🟣','⬛','🤍','💜'
        ];

        // ============================
        // MAIN APP
        // ============================
        function app() {
            return {
                daysRemaining: 0,
                weeksRemainingText: '',
                endDateDisplay: '',
                todayDisplay: '',
                isSyncing: false,
                isDark: false,
                interfaceMode: 1,
                
                initApp() {
                    this.initTheme();
                    this.initInterface();
                    this.calculateTime();
                    setInterval(() => this.calculateTime(), 60000);
                    
                    window.addEventListener('tracker-save', () => {
                        this.isSyncing = true;
                        setTimeout(() => this.isSyncing = false, 800);
                    });
                },

                initTheme() {
                    const saved = localStorage.getItem('theme_preference');
                    if (saved === 'dark') {
                        this.isDark = true;
                        document.documentElement.classList.add('dark');
                    } else {
                        this.isDark = false;
                        document.documentElement.classList.remove('dark');
                    }
                },
                
                setTheme(val) {
                    this.isDark = (val === 'dark');
                    if (this.isDark) {
                        document.documentElement.classList.add('dark');
                        localStorage.setItem('theme_preference', 'dark');
                    } else {
                        document.documentElement.classList.remove('dark');
                        localStorage.setItem('theme_preference', 'light');
                    }
                },

                initInterface() {
                    const saved = localStorage.getItem('interface_mode');
                    if (saved) {
                        this.interfaceMode = parseInt(saved);
                    }
                },

                setInterface(mode) {
                    this.interfaceMode = mode;
                    localStorage.setItem('interface_mode', mode);
                },

                calculateTime() {
                    const startDate = new Date(2026, 1, 17);
                    const endDate = new Date(startDate);
                    endDate.setDate(endDate.getDate() + 84);
                    
                    const ruDate = new Intl.DateTimeFormat('ru-RU', { day: 'numeric', month: 'long', year: 'numeric' });
                    this.endDateDisplay = ruDate.format(endDate).replace(' г.', ' г.');

                    const now = new Date();
                    this.todayDisplay = new Intl.DateTimeFormat('ru-RU', { weekday: 'long', day: 'numeric', month: 'long' }).format(now);

                    const today = new Date();
                    today.setHours(0, 0, 0, 0);
                    const diffTime = endDate - today;
                    const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
                    
                    if (diffDays <= 0) {
                        this.daysRemaining = 0;
                        this.weeksRemainingText = "Финиш!";
                    } else {
                        this.daysRemaining = diffDays;
                        const weeks = Math.floor(diffDays / 7);
                        const days = diffDays % 7;
                        
                        let text = "";
                        if (weeks > 0) {
                           text += `${weeks} ${this.getDeclension(weeks, ['неделя', 'недели', 'недель'])}`; 
                        }
                        if (days > 0) {
                            if (text) text += " ";
                            text += `${days} ${this.getDeclension(days, ['день', 'дня', 'дней'])}`;
                        }
                        if (!text) text = "Меньше дня";
                        
                        this.weeksRemainingText = text;
                    }
                },

                getDeclension(number, titles) {
                    const cases = [2, 0, 1, 1, 1, 2];
                    return titles[(number % 100 > 4 && number % 100 < 20) ? 2 : cases[(number % 10 < 5) ? number % 10 : 5]];
                }
            }
        }

        // ============================
        // TRACKER
        // ============================
        function tracker(id, storageKey, initialDefaultHabits) {
            return {
                habits: [],
                days: [],
                weeks: [],
                totalProgress: 0,
                v2DayIndex: 0,
                emojiPickerOpen: false,
                emojiPickerX: 0,
                emojiPickerY: 0,
                emojiPickerHabitIndex: -1,
                emojiPickerIconType: 1, // 1 = icon, 2 = icon2
                emojiList: EMOJI_LIST,
                
                // Habit Settings Modal
                habitSettingsOpen: false,
                habitSettingsIndex: -1,
                colorPalette: [
                    '#ef4444', '#f97316', '#f59e0b', '#eab308', '#84cc16',
                    '#22c55e', '#10b981', '#14b8a6', '#06b6d4', '#0ea5e9',
                    '#3b82f6', '#6366f1', '#8b5cf6', '#a855f7', '#d946ef',
                    '#ec4899', '#f43f5e', '#78716c', '#64748b', '#1e293b'
                ],
                dayNames: ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'],
                
                init() {
                    const startDate = new Date(2026, 1, 17);
                    
                    const dayNames = ['Вс', 'Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб'];
                    
                    this.days = [];
                    this.weeks = [];
                    
                    let currentWeek = { days: [] };
                    
                    for (let i = 0; i < 84; i++) {
                        const d = new Date(startDate);
                        d.setDate(d.getDate() + i);
                        
                        const dayObj = {
                            date: d,
                            dayNum: d.getDate(),
                            weekdayShort: dayNames[d.getDay()],
                            dateString: d.toISOString().split('T')[0],
                            index: i
                        };
                        
                        this.days.push(dayObj);
                        currentWeek.days.push(dayObj);
                        
                        if (currentWeek.days.length === 7 || i === 83) {
                            this.weeks.push(currentWeek);
                            currentWeek = { days: [] };
                        }
                    }

                    const todayIdx = this.days.findIndex(d => this.isToday(d.date));
                    this.v2DayIndex = todayIdx >= 0 ? todayIdx : 0;

                    const saved = localStorage.getItem(storageKey);
                    if (saved) {
                        try {
                            const parsed = JSON.parse(saved);
                            this.habits = parsed.habits || [];
                            this.habits.forEach(h => {
                                if (!h.checks) h.checks = {};
                                if (!h.icon2) h.icon2 = '';
                                if (!h.subtitle) h.subtitle = '';
                                if (!h.color) h.color = '#3b82f6';
                                if (!h.time) h.time = '';
                                if (!h.repeatDays) h.repeatDays = [0, 1, 2, 3, 4, 5, 6];
                                if (id === 'main' && h.name === 'Режим') h.isThreeState = true;
                            });
                        } catch (e) {
                            console.error('Data corrupted', e);
                            this.habits = [];
                        }
                    } else {
                        if (initialDefaultHabits && initialDefaultHabits.length > 0) {
                            this.habits = initialDefaultHabits.map((h, i) => ({
                                id: Date.now() + i,
                                name: h.name,
                                icon: h.icon,
                                icon2: h.icon2 || '',
                                subtitle: h.subtitle || '',
                                isThreeState: h.isThreeState || false,
                                checks: {}
                            }));
                        }
                    }
                    
                    this.calculateProgress();
                },
                
                get dateRangeDisplay() {
                    if (this.days.length === 0) return '';
                    const start = this.days[0].date;
                    const end = this.days[this.days.length - 1].date;
                    const fmt = new Intl.DateTimeFormat('ru-RU', { day: 'numeric', month: 'short', year: 'numeric' });
                    return `${fmt.format(start)} — ${fmt.format(end)}`;
                },
                
                isToday(dateObj) {
                    const today = new Date();
                    return dateObj.getDate() === today.getDate() &&
                           dateObj.getMonth() === today.getMonth() &&
                           dateObj.getFullYear() === today.getFullYear();
                },

                v2PrevDay() {
                    if (this.v2DayIndex > 0) this.v2DayIndex--;
                },
                v2NextDay() {
                    if (this.v2DayIndex < this.days.length - 1) this.v2DayIndex++;
                },
                v2DateTitle() {
                    if (this.v2DayIndex < 0 || this.v2DayIndex >= this.days.length) return '';
                    const d = this.days[this.v2DayIndex];
                    if (this.isToday(d.date)) return 'Сегодня';
                    return new Intl.DateTimeFormat('ru-RU', { weekday: 'short', day: 'numeric', month: 'long' }).format(d.date);
                },
                
                getCheckValue(habitIndex, dayIndex) {
                    const h = this.habits[habitIndex];
                    if (!h || !h.checks) return 0;
                    return h.checks[dayIndex] || 0;
                },
                
                toggleCheck(habitIndex, dayIndex) {
                    const h = this.habits[habitIndex];
                    const current = h.checks[dayIndex] || 0;
                    let next = 0;
                    
                    if (h.isThreeState) {
                        if (current === 0) next = 0.5;
                        else if (current === 0.5) next = 1;
                        else next = 0;
                    } else {
                        next = current === 0 ? 1 : 0;
                    }
                    
                    h.checks[dayIndex] = next;
                    this.saveData();
                    return next;
                },

                toggleCheckWithCelebration(habitIndex, dayIndex, event) {
                    const prev = this.getCheckValue(habitIndex, dayIndex);
                    const next = this.toggleCheck(habitIndex, dayIndex);
                    
                    const rect = event.currentTarget.getBoundingClientRect();
                    const cx = rect.left + rect.width / 2;
                    const cy = rect.top + rect.height / 2;

                    // Pop animation on the button
                    const btn = event.currentTarget.querySelector('div');
                    if (btn) {
                        btn.classList.remove('check-pop');
                        void btn.offsetWidth;
                        btn.classList.add('check-pop');
                    }

                    if (next === 1) {
                        // Full check — big celebration!
                        const celebTypes = ['confetti', 'coins', 'stars', 'hearts', 'fire'];
                        const randomType = celebTypes[Math.floor(Math.random() * celebTypes.length)];
                        
                        if (randomType === 'coins') {
                            CelebrationEngine.playCoinSound();
                        } else {
                            CelebrationEngine.playCheckSound();
                        }
                        
                        CelebrationEngine.spawnParticles(cx, cy, randomType);
                        CelebrationEngine.spawnRipple(cx, cy, this.getColor(this.getDayProgress(dayIndex)));

                        // Check if full day completed
                        const dayProgress = this.getDayProgress(dayIndex);
                        if (dayProgress >= 100) {
                            setTimeout(() => {
                                CelebrationEngine.bigCelebration(cx, cy);
                            }, 300);
                        }
                    } else if (next === 0.5) {
                        // Half check — softer celebration
                        CelebrationEngine.playHalfCheckSound();
                        CelebrationEngine.spawnParticles(cx, cy, 'stars');
                    } else {
                        // Uncheck
                        CelebrationEngine.playUncheckSound();
                    }
                },

                // Emoji Picker
                openEmojiPicker(habitIndex, iconType, event) {
                    const rect = event.currentTarget.getBoundingClientRect();
                    this.emojiPickerX = Math.min(rect.left, window.innerWidth - 340);
                    this.emojiPickerY = rect.bottom + 8;
                    
                    if (this.emojiPickerY + 260 > window.innerHeight) {
                        this.emojiPickerY = rect.top - 260;
                    }
                    
                    this.emojiPickerHabitIndex = habitIndex;
                    this.emojiPickerIconType = iconType || 1; // 1 = icon, 2 = icon2
                    this.emojiPickerOpen = true;
                },

                setHabitEmoji(emoji) {
                    if (this.emojiPickerHabitIndex >= 0 && this.emojiPickerHabitIndex < this.habits.length) {
                        if (this.emojiPickerIconType === 2) {
                            this.habits[this.emojiPickerHabitIndex].icon2 = emoji;
                        } else {
                            this.habits[this.emojiPickerHabitIndex].icon = emoji;
                        }
                        this.saveData();
                    }
                    this.emojiPickerOpen = false;
                },

                // Habit Settings
                openHabitSettings(index) {
                    this.habitSettingsIndex = index;
                    this.habitSettingsOpen = true;
                },

                closeHabitSettings() {
                    this.habitSettingsOpen = false;
                    this.habitSettingsIndex = -1;
                },

                setHabitColor(color) {
                    if (this.habitSettingsIndex >= 0) {
                        this.habits[this.habitSettingsIndex].color = color;
                        this.saveData();
                    }
                },

                toggleRepeatDay(dayIndex) {
                    if (this.habitSettingsIndex >= 0) {
                        const h = this.habits[this.habitSettingsIndex];
                        const idx = h.repeatDays.indexOf(dayIndex);
                        if (idx > -1) {
                            h.repeatDays.splice(idx, 1);
                        } else {
                            h.repeatDays.push(dayIndex);
                            h.repeatDays.sort();
                        }
                        this.saveData();
                    }
                },

                getHabitSettings() {
                    if (this.habitSettingsIndex >= 0 && this.habitSettingsIndex < this.habits.length) {
                        return this.habits[this.habitSettingsIndex];
                    }
                    return null;
                },

                shouldShowHabitOnDay(habit, dayIndex) {
                    if (!habit.repeatDays || habit.repeatDays.length === 0) return true;
                    const dayOfWeek = this.days[dayIndex].date.getDay();
                    // Convert Sunday=0 to Monday=0 format
                    const adjustedDay = dayOfWeek === 0 ? 6 : dayOfWeek - 1;
                    return habit.repeatDays.includes(adjustedDay);
                },
                
                addHabit() {
                    this.habits.push({
                        id: Date.now(),
                        name: '',
                        icon: '🔹',
                        icon2: '',
                        isThreeState: false,
                        color: '#3b82f6', // default blue
                        time: '',
                        repeatDays: [0, 1, 2, 3, 4, 5, 6], // all days by default
                        checks: {}
                    });
                    this.saveData();
                },
                
                deleteHabit(index) {
                    if (confirm('Удалить эту привычку?')) {
                        this.habits.splice(index, 1);
                        this.saveData();
                    }
                },
                
                calculateProgress() {
                    if (this.habits.length === 0) {
                        this.totalProgress = 0;
                        return;
                    }
                    
                    let totalPoints = 0;
                    const maxPoints = this.habits.length * 84;
                    
                    this.habits.forEach(h => {
                        if (h.checks) {
                            Object.values(h.checks).forEach(val => {
                                totalPoints += parseFloat(val) || 0;
                            });
                        }
                    });
                    
                    this.totalProgress = maxPoints === 0 ? 0 : (totalPoints / maxPoints) * 100;
                },
                
                getDayProgress(dayIndex) {
                    if (this.habits.length === 0) return 0;
                    let total = 0;
                    this.habits.forEach(h => {
                        total += parseFloat(h.checks[dayIndex] || 0);
                    });
                    return (total / this.habits.length) * 100;
                },
                
                saveData() {
                    this.calculateProgress();
                    const data = {
                        habits: this.habits,
                        lastUpdated: Date.now()
                    };
                    localStorage.setItem(storageKey, JSON.stringify(data));
                    window.dispatchEvent(new CustomEvent('tracker-save'));
                },
                
                getColor(percent) {
                    const p = Math.min(Math.max(percent, 0), 100);
                    if (p < 50) return '#ef4444';
                    if (p < 80) return '#f97316';
                    return '#22c55e';
                }
            }
        }
    </script>
</body>
</html>

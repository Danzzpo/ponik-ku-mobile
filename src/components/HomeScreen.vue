<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden font-sans flex flex-col transition-colors duration-300">
    
    <div class="w-full px-6 pt-8 pb-4 bg-white dark:bg-gray-900 z-20 shrink-0">
      <div class="flex justify-between items-center">
        <div>
          <h1 class="font-bold text-[24px] leading-[28px] text-black dark:text-white">Hi, User!</h1>
        </div>
        <div class="flex items-center space-x-4">
          <button class="relative">
             <Bell :size="24" class="text-black dark:text-white" />
             <div class="absolute top-0 right-0 w-2 h-2 bg-red-500 rounded-full border border-white dark:border-gray-900"></div>
          </button>
          
          <button 
            @click="$emit('change-screen', 'dashboard')"
            class="w-[30px] h-[30px] bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden border border-gray-300 dark:border-gray-600 hover:ring-2 hover:ring-green-500 transition"
          >
            <User :size="24" class="m-auto mt-0.5 text-gray-500 dark:text-gray-300" />
          </button>
        </div>
      </div>
      <div class="w-full h-[1px] bg-black/10 dark:bg-white/10 mt-4"></div>
      <div class="mt-2 flex items-center space-x-1">
        <span class="font-light text-[16px] text-black dark:text-white">Welcome to</span>
        <span class="font-bold text-[18px] text-[#17941F]">ponik-ku</span>
      </div>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 pb-24 space-y-6">
       
       <div class="w-full h-[166px] bg-white dark:bg-gray-800 border border-black/5 dark:border-white/10 rounded-[20px] shadow-lg relative p-4 transition-colors duration-300">
          <span class="absolute right-4 top-4 font-bold text-[12px] text-black dark:text-white">Malang, Indonesia</span>
          <div class="absolute left-4 top-4 flex flex-col">
             <span class="font-medium text-[16px] text-black dark:text-white">12, January 2026</span>
             <span class="font-bold text-[14px] text-black/40 dark:text-white/40 mt-1">Cloudy</span>
          </div>
          <div class="absolute left-4 bottom-4 font-bold text-[40px] leading-[47px] text-black dark:text-white flex items-start">
             23 <span class="text-[15px] mt-1 ml-1">°C</span>
          </div>
          <CloudRain :size="64" class="absolute right-4 bottom-4 text-blue-400 opacity-80" />
       </div>

       <div class="space-y-4 mt-2">
        <div class="w-full h-[126px] bg-white dark:bg-gray-800 border border-black/30 dark:border-white/20 rounded-[10px] shadow-md relative overflow-hidden group cursor-pointer">
           <div class="absolute left-[20px] top-[18px] right-[20px] bottom-[18px] bg-[#F9F9F9] dark:bg-gray-700 shadow-inner rounded-[5px] flex items-center justify-center">
              <PlayCircle :size="32" class="text-black/60 dark:text-white/60 group-hover:text-[#17941F] transition" />
           </div>
           <span class="absolute right-4 top-2 text-[12px] font-bold text-black dark:text-white">News</span>
        </div>
        <div class="w-full h-[126px] bg-white dark:bg-gray-800 border border-black/30 dark:border-white/20 rounded-[10px] shadow-md relative overflow-hidden group cursor-pointer">
           <div class="absolute left-[20px] top-[18px] right-[20px] bottom-[18px] bg-[#F9F9F9] dark:bg-gray-700 shadow-inner rounded-[5px] flex items-center justify-center">
              <PlayCircle :size="32" class="text-black/60 dark:text-white/60 group-hover:text-[#17941F] transition" />
           </div>
           <span class="absolute bottom-2 left-0 right-0 text-center text-[12px] font-bold text-black/60 dark:text-white/60">Video</span>
        </div>
      </div>

      <div class="w-full h-[40px] bg-[#17941F] rounded-[5px] shadow-md flex items-center justify-between px-4 cursor-pointer hover:bg-[#137a1a] transition">
        <span class="font-semibold text-[13px] text-white">Device 1</span>
        <ChevronDown :size="20" color="white" />
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div class="bg-[#F9F9F9] dark:bg-gray-800 rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px] transition-colors">
          <Thermometer :size="20" class="absolute left-2 top-2 text-red-500" />
          <span class="text-[12px] font-semibold mb-1 text-black dark:text-white">Temp. Control</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60">28</span>
             <span class="text-[12px] font-bold text-black/60 dark:text-white/60 ml-1 mb-0.5">°C</span>
          </div>
        </div>
        <div class="bg-[#F9F9F9] dark:bg-gray-800 rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px] transition-colors">
          <Sun :size="20" class="absolute left-2 top-2 text-orange-400" />
          <span class="text-[12px] font-semibold mb-1 text-black dark:text-white">Intensity</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60">120</span>
             <span class="text-[12px] font-bold text-black/60 dark:text-white/60 ml-1 mb-0.5">Cd</span>
          </div>
        </div>
        <div class="bg-[#F9F9F9] dark:bg-gray-800 rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px] transition-colors">
          <Droplets :size="20" class="absolute left-2 top-2 text-blue-400" />
          <span class="text-[12px] font-semibold mb-1 text-black dark:text-white">Humidity</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60">60</span>
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60 ml-1 mb-0.5">%</span>
          </div>
        </div>
        <div class="bg-[#F9F9F9] dark:bg-gray-800 rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px] transition-colors">
          <FlaskConical :size="20" class="absolute left-2 top-2 text-purple-500" />
          <span class="text-[12px] font-semibold mb-1 text-black dark:text-white">Water pH</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60">7.2</span>
             <span class="text-[16px] font-bold text-black/60 dark:text-white/60 ml-1 mb-0.5">pH</span>
          </div>
        </div>
      </div>

      <div class="w-full h-[40px] bg-[#17941F] rounded-[5px] shadow-md flex flex-col items-center justify-center relative">
         <span class="font-semibold text-[13px] text-white">Status</span>
         <span class="font-bold text-[10px] text-white opacity-90">Bad / Normal / Good</span>
      </div>

    </div>

    <div class="absolute bottom-0 left-0 w-full h-[65px] bg-[#17941F] rounded-t-[0px] rounded-b-[0px] flex justify-around items-center px-2 z-30 shadow-[0_-4px_10px_rgba(0,0,0,0.1)]">
      <button class="flex flex-col items-center justify-center w-14 group">
        <div class="bg-white/20 p-1.5 rounded-lg mb-0.5">
           <Home :size="20" color="white" />
        </div>
        <span class="text-[10px] font-bold text-black">Home</span>
      </button>
      <button 
        @click="$emit('change-screen', 'info')" 
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5">
           <FileText :size="20" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Info</span>
      </button> 
      <button 
        @click="$emit('change-screen', 'add-device')"
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5 relative">
           <PlusCircle :size="28" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Add</span>
      </button>
      <button 
        @click="$emit('change-screen', 'calculator')" 
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5">
           <Calculator :size="20" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Calc</span>
      </button>
    </div>

  </div>
</template>

<script setup>
import { 
  Bell, User, PlayCircle, ChevronDown, Thermometer, Sun, 
  Droplets, FlaskConical, Home, FileText, PlusCircle, Calculator, CloudRain 
} from 'lucide-vue-next';
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
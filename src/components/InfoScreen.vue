<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden mx-auto font-sans flex flex-col transition-colors duration-300">
    
    <div class="w-full px-6 pt-8 pb-4 bg-white dark:bg-gray-900 z-20 shrink-0 border-b border-gray-100 dark:border-gray-800">
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
            class="w-[30px] h-[30px] bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden border border-gray-300 dark:border-gray-600 hover:ring-2 hover:ring-green-500 transition flex items-center justify-center"
          >
            <User :size="20" class="text-gray-500 dark:text-gray-300" />
          </button>
        </div>
      </div>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-4 py-6">
      
      <div class="space-y-4 mb-8">
        <div 
           @click="$emit('change-screen', 'info-detail')"
           class="w-full h-[52px] bg-white dark:bg-gray-800 border border-black/5 dark:border-white/10 rounded-[10px] shadow-sm flex items-center justify-between px-4 cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-700 transition group"
        >
           <span class="font-normal text-[18px] text-black dark:text-white">Data of Plant</span>
           <ChevronDown :size="24" class="text-black dark:text-white group-hover:text-[#17941F] transition" />
        </div>

        <div class="w-full h-[52px] bg-white dark:bg-gray-800 border border-black/5 dark:border-white/10 rounded-[10px] shadow-sm flex items-center justify-between px-4 cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-700 transition group">
           <span class="font-normal text-[18px] text-black dark:text-white">Data of Flowers</span>
           <ChevronDown :size="24" class="text-black dark:text-white group-hover:text-[#17941F] transition" />
        </div>

        <div class="w-full h-[52px] bg-white dark:bg-gray-800 border border-black/5 dark:border-white/10 rounded-[10px] shadow-sm flex items-center justify-between px-4 cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-700 transition group">
           <span class="font-normal text-[18px] text-black dark:text-white">Data of Vegetabels</span>
           <ChevronDown :size="24" class="text-black dark:text-white group-hover:text-[#17941F] transition" />
        </div>

        <div class="w-full h-[52px] bg-white dark:bg-gray-800 border border-black/5 dark:border-white/10 rounded-[10px] shadow-sm flex items-center justify-between px-4 cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-700 transition group">
           <span class="font-normal text-[18px] text-black dark:text-white">Tutorial</span>
           <ChevronDown :size="24" class="text-black dark:text-white group-hover:text-[#17941F] transition" />
        </div>
      </div>

      <div class="w-full bg-[#F9F9F9] dark:bg-gray-800 rounded-[5px] shadow-md p-4 flex flex-col items-center justify-center relative min-h-[166px] cursor-pointer group transition-colors">
         <div class="w-[50px] h-[50px] bg-black/10 dark:bg-white/10 rounded-full flex items-center justify-center mb-2 group-hover:bg-[#17941F] transition duration-300">
            <Play :size="24" class="text-black dark:text-white group-hover:text-white ml-1" />
         </div>
         <span class="font-medium text-[15px] text-black dark:text-white">Video</span>
         
         <div class="flex space-x-1 mt-4">
            <div class="w-2 h-2 bg-black dark:bg-white rounded-full"></div>
            <div class="w-2 h-2 bg-black dark:bg-white rounded-full"></div>
            <div class="w-2 h-2 bg-black dark:bg-white rounded-full"></div>
         </div>
      </div>

    </div>

    <div class="absolute bottom-0 left-0 w-full h-[65px] bg-[#17941F] rounded-t-[0px] rounded-b-[0px] md:rounded-b-[20px] flex justify-around items-center px-2 z-30 shadow-[0_-4px_10px_rgba(0,0,0,0.1)]">
      
      <button 
        @click="$emit('change-screen', 'home')"
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5">
           <Home :size="20" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Home</span>
      </button>

      <button class="flex flex-col items-center justify-center w-14 group">
        <div class="bg-white/20 p-1.5 rounded-lg mb-0.5">
           <FileText :size="20" color="white" /> </div>
        <span class="text-[10px] font-bold text-black">Info</span>
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
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition">
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
  Bell, User, ChevronDown, Play,
  Home, FileText, PlusCircle, Calculator 
} from 'lucide-vue-next';

defineEmits(['change-screen']);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
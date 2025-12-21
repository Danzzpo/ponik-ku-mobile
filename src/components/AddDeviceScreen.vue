<template>
  <div class="w-full h-full bg-white relative overflow-hidden mx-auto font-sans flex flex-col">
    
    <div class="w-full px-6 pt-8 pb-4 bg-white z-20 shrink-0 border-b border-gray-100">
      <div class="flex justify-between items-center">
        <div>
          <h1 class="font-bold text-[24px] leading-[28px] text-black">Hi, User!</h1>
        </div>
        
        <div class="flex items-center space-x-4">
          <button class="relative">
             <Bell :size="24" color="black" />
             <div class="absolute top-0 right-0 w-2 h-2 bg-red-500 rounded-full border border-white"></div>
          </button>
          
          <button 
            @click="$emit('change-screen', 'dashboard')"
            class="w-[30px] h-[30px] bg-gray-200 rounded-full overflow-hidden border border-gray-300 hover:ring-2 hover:ring-green-500 transition flex items-center justify-center"
          >
            <User :size="20" class="text-gray-500" />
          </button>
        </div>
      </div>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 pb-28 relative">
      
      <div class="w-[200px] h-[200px] mx-auto mt-6 bg-gray-100 rounded-full flex items-center justify-center relative overflow-hidden">
        <Cpu :size="100" class="text-[#17941F]/30" />
        </div>

      <div class="w-full bg-[#17941F] rounded-[10px] p-6 mt-6 shadow-md text-center">
        <p class="font-normal text-[20px] leading-[23px] text-white">
          Have your own device? Add your device and start controlling sensor.
        </p>
      </div>

      <div class="w-full bg-[#DBDBDB] rounded-[10px] p-5 mt-4 shadow-sm flex items-center justify-between cursor-pointer hover:bg-gray-300 transition group">
        <span class="font-semibold text-[20px] text-black">Have no device?</span>
        <div class="w-[50px] h-[50px] flex items-center justify-center group-hover:scale-110 transition">
          <Smartphone :size="40" class="text-black" />
        </div>
      </div>

      <div class="w-full bg-[#17941F] rounded-[10px] p-5 mt-4 shadow-md flex items-center justify-between cursor-pointer hover:bg-[#137a1a] transition group">
        <span class="font-normal text-[20px] text-white">Visit & Buy Property?</span>
        <div class="w-[50px] h-[50px] flex items-center justify-center group-hover:scale-110 transition">
           <ShoppingBag :size="40" class="text-white" />
        </div>
      </div>

    </div>

    <button class="absolute bottom-[90px] right-6 bg-[#17941F] text-white rounded-[20px] px-4 py-2 flex items-center shadow-lg hover:bg-[#137a1a] transition active:scale-95 z-40">
      <Plus :size="24" class="mr-2" />
      <span class="font-medium text-[17px]">ADD DEVICE</span>
    </button>

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

      <button 
        @click="$emit('change-screen', 'info')"
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5">
           <FileText :size="20" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Info</span>
      </button>

      <button class="flex flex-col items-center justify-center w-14 group">
        <div class="bg-white/20 p-1.5 rounded-lg mb-0.5 relative">
           <PlusCircle :size="28" color="white" />
        </div>
        <span class="text-[10px] font-bold text-black">Add</span>
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
  Bell, User, Cpu, Smartphone, ShoppingBag, Plus,
  Home, FileText, PlusCircle, Calculator 
} from 'lucide-vue-next';

defineEmits(['change-screen']);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>

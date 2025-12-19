<template>
  <div class="w-full h-screen md:w-[360px] md:h-[800px] bg-white md:rounded-[30px] shadow-2xl relative overflow-hidden ring-0 md:ring-8 ring-black mx-auto font-sans flex flex-col">
    
    <div class="w-full px-6 pt-8 pb-4 bg-white z-20 shrink-0">
      <div class="flex justify-between items-center">
        <div>
          <h1 class="font-bold text-[24px] leading-[28px] text-black">Hi, User!</h1>
        </div>
        
        <div class="flex items-center space-x-4">
          <button class="relative">
             <Bell :size="24" color="black" />
             <div class="absolute top-0 right-0 w-2 h-2 bg-red-500 rounded-full border border-white"></div>
          </button>
          <div class="w-[30px] h-[30px] bg-gray-200 rounded-full overflow-hidden border border-gray-300">
            <User :size="24" class="m-auto mt-0.5 text-gray-500" />
          </div>
        </div>
      </div>

      <div class="w-full h-[1px] bg-black/10 mt-4"></div>

      <div class="mt-2 flex items-center space-x-1">
        <span class="font-light text-[16px] text-black">Welcome to</span>
        <span class="font-bold text-[18px] text-[#17941F]">ponik-ku</span>
      </div>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 pb-24 space-y-6">
      
      <div class="space-y-4 mt-2">
        
        <div class="w-full h-[126px] bg-white border border-black/30 rounded-[10px] shadow-[2px_2px_12px_rgba(0,0,0,0.15)] relative overflow-hidden group cursor-pointer">
           <div class="absolute left-[20px] top-[18px] right-[20px] bottom-[18px] bg-[#F9F9F9] shadow-inner rounded-[5px] flex items-center justify-center">
              <PlayCircle :size="32" class="text-black/60 group-hover:text-[#17941F] transition" />
           </div>
           <span class="absolute right-4 top-2 text-[12px] font-bold text-black">News</span>
        </div>

        <div class="w-full h-[126px] bg-white border border-black/30 rounded-[10px] shadow-[2px_2px_12px_rgba(0,0,0,0.15)] relative overflow-hidden group cursor-pointer">
           <div class="absolute left-[20px] top-[18px] right-[20px] bottom-[18px] bg-[#F9F9F9] shadow-inner rounded-[5px] flex items-center justify-center">
              <PlayCircle :size="32" class="text-black/60 group-hover:text-[#17941F] transition" />
           </div>
           <span class="absolute bottom-2 left-0 right-0 text-center text-[12px] font-bold text-black/60">Video</span>
        </div>

      </div>

      <div class="w-full h-[40px] bg-[#17941F] rounded-[5px] shadow-[2px_3px_4px_rgba(0,0,0,0.15)] flex items-center justify-between px-4 cursor-pointer hover:bg-[#137a1a] transition">
        <span class="font-semibold text-[13px] text-white">Device 1</span>
        <ChevronDown :size="20" color="white" />
      </div>

      <div class="grid grid-cols-2 gap-4">
        
        <div class="bg-[#F9F9F9] rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px]">
          <Thermometer :size="20" class="absolute left-2 top-2 text-red-500" />
          <span class="text-[12px] font-semibold mb-1">Temp. Control</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[12px] font-bold text-black/60 ml-1 mb-0.5">°C</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px]">
          <Sun :size="20" class="absolute left-2 top-2 text-orange-400" />
          <span class="text-[12px] font-semibold mb-1">Intensity</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[12px] font-bold text-black/60 ml-1 mb-0.5">Cd</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px]">
          <Droplets :size="20" class="absolute left-2 top-2 text-blue-400" />
          <span class="text-[12px] font-semibold mb-1">Humidity</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[12px] font-bold text-black/60 ml-1 mb-0.5">%</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] p-3 shadow-md flex flex-col items-center justify-center relative h-[88px]">
          <FlaskConical :size="20" class="absolute left-2 top-2 text-purple-500" />
          <span class="text-[12px] font-semibold mb-1">Water pH</span>
          <div class="flex items-end">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[12px] font-bold text-black/60 ml-1 mb-0.5">pH</span>
          </div>
        </div>

      </div>

      <div class="w-full h-[40px] bg-[#17941F] rounded-[5px] shadow-[2px_3px_4px_rgba(0,0,0,0.15)] flex flex-col items-center justify-center relative">
         <span class="font-semibold text-[13px] text-white">Status</span>
         <span class="font-bold text-[10px] text-white opacity-90">Bad / Normal / Good</span>
      </div>

    </div>

    <div class="absolute bottom-0 left-0 w-full h-[65px] bg-[#17941F] rounded-t-[0px] rounded-b-[0px] md:rounded-b-[20px] flex justify-around items-center px-2 z-30 shadow-[0_-4px_10px_rgba(0,0,0,0.1)]">
      
      <button class="flex flex-col items-center justify-center w-14 group">
        <div class="bg-white/20 p-1.5 rounded-lg mb-0.5">
           <Home :size="20" color="white" />
        </div>
        <span class="text-[10px] font-bold text-black">Home</span>
      </button>

      <button class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition">
        <div class="p-1.5 mb-0.5">
           <FileText :size="20" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Info</span>
      </button>

      <button class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition">
        <div class="p-1.5 mb-0.5 relative">
           <PlusCircle :size="28" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Add Device</span>
      </button>

      <button class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition">
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
  Bell, 
  User, 
  PlayCircle, 
  ChevronDown, 
  Thermometer, 
  Sun, 
  Droplets, 
  FlaskConical,
  Home,
  FileText,
  PlusCircle,
  Calculator
} from 'lucide-vue-next';

// Tidak ada logic khusus, hanya tampilan
</script>

<style scoped>
/* Hilangkan Scrollbar */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}
.scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
}
</style>
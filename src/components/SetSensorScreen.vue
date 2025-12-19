<template>
  <div class="w-full h-full bg-white relative overflow-hidden mx-auto font-sans flex flex-col">
    
    <div class="w-full h-[70px] flex items-center px-4 shrink-0 border-b border-gray-100 relative">
      <button 
        @click="$emit('change-screen', 'home')" 
        class="p-2 -ml-2 hover:bg-gray-100 rounded-full transition"
      >
         <ArrowLeft :size="24" color="black" />
      </button>
      
      <h1 class="font-bold text-[20px] text-black ml-4">Atur Sensor</h1>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 py-6">
      
      <div class="flex justify-between items-center mb-6">
        <span class="font-bold text-[20px] text-black">Auto</span>
        
        <button 
          @click="isAuto = !isAuto"
          class="w-[63px] h-[32px] rounded-full relative transition-colors duration-300 focus:outline-none"
          :class="isAuto ? 'bg-[#17941F]' : 'bg-[#ADABAB]'"
        >
          <div 
            class="absolute top-[4px] w-[24px] h-[24px] bg-white rounded-full shadow-sm transition-all duration-300 flex items-center justify-center"
            :class="isAuto ? 'left-[35px]' : 'left-[4px]'"
          >
             <div class="w-[6px] h-[6px] rounded-full bg-gray-300"></div>
          </div>
        </button>
      </div>

      <div class="flex items-center justify-center space-x-4 mb-6">
        <div class="h-[1px] bg-black/25 flex-1"></div>
        <span class="font-medium text-[15px] text-black whitespace-nowrap">Konfigurasi Sensor</span>
        <div class="h-[1px] bg-black/25 flex-1"></div>
      </div>

      <h2 class="font-bold text-[20px] text-black mb-4">Daftar Konfigurasi</h2>

      <div class="grid grid-cols-2 gap-4 pb-10">
        
        <div class="bg-[#F9F9F9] rounded-[5px] h-[101px] shadow-[5px_5px_4px_rgba(0,0,0,0.15)] flex flex-col items-center justify-center relative hover:scale-[1.02] transition cursor-pointer">
          <Thermometer :size="24" class="absolute left-3 top-3 text-red-500" />
          
          <span class="text-[13px] font-semibold text-black mt-4">Temp. Control</span>
          
          <div class="flex items-end justify-between w-full px-6 mt-2">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[16px] font-bold text-black/60">°C</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] h-[101px] shadow-[0px_4px_4px_rgba(0,0,0,0.15)] flex flex-col items-center justify-center relative hover:scale-[1.02] transition cursor-pointer">
          <Sun :size="24" class="absolute left-3 top-3 text-orange-400" />
          <span class="text-[13px] font-semibold text-black mt-4">Intensity</span>
          <div class="flex items-end justify-between w-full px-6 mt-2">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[16px] font-bold text-black/60">Cd</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] h-[101px] shadow-[5px_5px_4px_rgba(0,0,0,0.15)] flex flex-col items-center justify-center relative hover:scale-[1.02] transition cursor-pointer">
          <Droplets :size="24" class="absolute left-3 top-3 text-blue-400" />
          <span class="text-[13px] font-semibold text-black mt-4">Humidity</span>
          <div class="flex items-end justify-between w-full px-6 mt-2">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[16px] font-bold text-black/60">%</span>
          </div>
        </div>

        <div class="bg-[#F9F9F9] rounded-[5px] h-[101px] shadow-[5px_5px_4px_rgba(0,0,0,0.15)] flex flex-col items-center justify-center relative hover:scale-[1.02] transition cursor-pointer">
          <FlaskConical :size="24" class="absolute left-3 top-3 text-purple-500" />
          <span class="text-[13px] font-semibold text-black mt-4">Water pH</span>
          <div class="flex items-end justify-between w-full px-6 mt-2">
             <span class="text-[16px] font-bold text-black/60">00</span>
             <span class="text-[16px] font-bold text-black/60">pH</span> </div>
        </div>

      </div>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue';
import { ArrowLeft, Thermometer, Sun, Droplets, FlaskConical } from 'lucide-vue-next';

const emit = defineEmits(['change-screen']);
const isAuto = ref(false); // State untuk toggle switch
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
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

    <div class="flex-1 flex items-center justify-center px-6 bg-gray-50/50 dark:bg-gray-950/50">
      
      <div class="w-[300px] bg-white dark:bg-gray-800 rounded-[20px] shadow-lg p-6 flex flex-col items-center relative transition-colors">
        
        <div class="w-full mb-6 relative">
          <div class="relative w-full h-[38px] border border-black/30 dark:border-white/30 rounded-[5px] flex items-center bg-white dark:bg-gray-700 overflow-hidden">
            <select 
              v-model="selectedPlant" 
              class="w-full h-full bg-transparent outline-none px-3 text-[14px] text-black dark:text-white appearance-none relative z-10 cursor-pointer"
            >
              <option value="" disabled selected class="text-gray-500">Choose a Plant</option>
              <option value="Pakcoy" class="text-black">Pakcoy</option>
              <option value="Selada" class="text-black">Selada</option>
              <option value="Bayam" class="text-black">Bayam</option>
              <option value="Kangkung" class="text-black">Kangkung</option>
            </select>
            <ChevronDown :size="20" class="absolute right-2 text-gray-500 dark:text-gray-300 z-0" />
          </div>
        </div>

        <div class="w-full mb-6">
          <label class="block text-center text-[15px] text-black dark:text-white mb-2">Water Volume</label>
          <div class="w-full h-[41px] border border-black/30 dark:border-white/30 rounded-[5px] flex items-center px-3 bg-white dark:bg-gray-700 relative">
             <input 
               v-model="waterVolume" 
               type="number" 
               placeholder="0"
               class="w-full h-full bg-transparent outline-none text-[16px] font-medium text-black dark:text-white pr-8 text-center"
             />
             <span class="absolute right-3 text-[19px] font-semibold text-black/40 dark:text-white/40">L</span>
          </div>
        </div>

        <button 
          @click="calculateNutrition"
          class="w-[126px] h-[47px] bg-[#17941F] rounded-[20px] flex items-center justify-center shadow-md active:scale-95 transition hover:bg-[#137a1a] mb-8"
        >
          <span class="font-bold text-[14px] text-white">Calculate</span>
        </button>

        <div class="w-full flex flex-col items-center">
          <label class="block text-center text-[15px] text-black dark:text-white mb-2">AB Mix Nutrition</label>
          <div class="w-[163px] h-[41px] border border-black/30 dark:border-white/30 rounded-[5px] flex items-center justify-center px-2 bg-gray-50 dark:bg-gray-700 relative">
             <span class="font-bold text-[18px] text-[#17941F] dark:text-green-400">
               {{ nutritionResult }}
             </span>
             <span class="absolute right-2 text-[15px] font-semibold text-black/40 dark:text-white/40">mL/L</span>
          </div>
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

      <button class="flex flex-col items-center justify-center w-14 group">
        <div class="bg-white/20 p-1.5 rounded-lg mb-0.5">
           <Calculator :size="20" color="white" />
        </div>
        <span class="text-[10px] font-bold text-black">Calc</span>
      </button>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue';
import { 
  Bell, User, ChevronDown, 
  Home, FileText, PlusCircle, Calculator 
} from 'lucide-vue-next';

defineEmits(['change-screen']);

const selectedPlant = ref("");
const waterVolume = ref("");
const nutritionResult = ref(0);

const calculateNutrition = () => {
  if (!waterVolume.value || waterVolume.value <= 0) {
    alert("Masukkan volume air yang valid!");
    return;
  }
  if (!selectedPlant.value) {
    alert("Pilih tanaman terlebih dahulu!");
    return;
  }
  const ratio = 5; 
  nutritionResult.value = waterVolume.value * ratio;
};
</script>

<style scoped>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
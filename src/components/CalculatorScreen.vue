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

    <div class="flex-1 flex items-center justify-center px-6 bg-gray-50/50">
      
      <div class="w-[300px] bg-white rounded-[20px] shadow-[2px_2px_20px_rgba(0,0,0,0.15)] p-6 flex flex-col items-center relative">
        
        <div class="w-full mb-6 relative">
          <div class="relative w-full h-[38px] border border-black/30 rounded-[5px] flex items-center bg-white overflow-hidden">
            <select 
              v-model="selectedPlant" 
              class="w-full h-full bg-transparent outline-none px-3 text-[14px] text-black appearance-none relative z-10 cursor-pointer"
            >
              <option value="" disabled selected>Choose a Plant</option>
              <option value="Pakcoy">Pakcoy</option>
              <option value="Selada">Selada</option>
              <option value="Bayam">Bayam</option>
              <option value="Kangkung">Kangkung</option>
            </select>
            <ChevronDown :size="20" class="absolute right-2 text-gray-500 z-0" />
          </div>
        </div>

        <div class="w-full mb-6">
          <label class="block text-center text-[15px] text-black mb-2">Water Volume</label>
          <div class="w-full h-[41px] border border-black/30 rounded-[5px] flex items-center px-3 bg-white relative">
             <input 
               v-model="waterVolume" 
               type="number" 
               placeholder="0"
               class="w-full h-full bg-transparent outline-none text-[16px] font-medium text-black pr-8 text-center"
             />
             <span class="absolute right-3 text-[19px] font-semibold text-black/40">L</span>
          </div>
        </div>

        <button 
          @click="calculateNutrition"
          class="w-[126px] h-[47px] bg-[#17941F] rounded-[20px] flex items-center justify-center shadow-md active:scale-95 transition hover:bg-[#137a1a] mb-8"
        >
          <span class="font-bold text-[14px] text-white">Calculate</span>
        </button>

        <div class="w-full flex flex-col items-center">
          <label class="block text-center text-[15px] text-black mb-2">AB Mix Nutrition</label>
          <div class="w-[163px] h-[41px] border border-black/30 rounded-[5px] flex items-center justify-center px-2 bg-gray-50 relative">
             <span class="font-bold text-[18px] text-[#17941F]">
               {{ nutritionResult }}
             </span>
             <span class="absolute right-2 text-[15px] font-semibold text-black/40">mL/L</span>
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

// STATE DATA
const selectedPlant = ref("");
const waterVolume = ref("");
const nutritionResult = ref(0);

// FUNGSI HITUNG SEDERHANA
const calculateNutrition = () => {
  if (!waterVolume.value || waterVolume.value <= 0) {
    alert("Masukkan volume air yang valid!");
    return;
  }
  
  if (!selectedPlant.value) {
    alert("Pilih tanaman terlebih dahulu!");
    return;
  }

  // LOGIKA DUMMY:
  // Rumus: Volume Air (L) * 5mL (Standar umum hidroponik 5ml A + 5ml B per liter)
  // Anda bisa sesuaikan rumus ini nanti
  const ratio = 5; 
  nutritionResult.value = waterVolume.value * ratio;
};
</script>

<style scoped>
/* Agar input number tidak ada panah spin di kanan */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
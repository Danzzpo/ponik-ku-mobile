<template>
  <div class="w-full h-full bg-white relative overflow-hidden mx-auto font-sans flex flex-col">
    
    <div class="w-full h-[70px] flex items-center px-4 shrink-0 border-b border-gray-200 bg-white z-20">
      <button 
        @click="$emit('change-screen', 'info')" 
        class="p-2 -ml-2 hover:bg-gray-100 rounded-full transition"
      >
         <ArrowLeft :size="24" color="black" />
      </button>
      <h1 class="font-bold text-[20px] text-black ml-4">Information</h1>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 pb-24">
      
      <div class="w-full h-[40px] bg-[#FAFAFA]/90 rounded-[10px] flex items-center px-3 mt-6 mb-8 shadow-sm border border-black/5">
        <Search :size="18" class="text-gray-500 mr-2" />
        <input 
          type="text" 
          placeholder="Search" 
          class="w-full bg-transparent outline-none text-[17px] text-black placeholder-blue-500/60 font-sans"
        />
      </div>

      <div class="w-full border border-black/40 rounded-[20px] p-5 shadow-[2px_2px_12px_rgba(0,0,0,0.25)] relative mb-6">
        <h2 class="font-bold text-[20px] text-black text-center mb-2">Pakcoy</h2>
        <p class="font-normal text-[12px] leading-[14px] text-justify text-black">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente, voluptas quaerat molestiae dolorem nulla debitis? Deskripsi tentang tanaman pakcoy, kadar ph air yang bagus untuk pakcoy antara a-z, range volume air yang dibutuhkan pada penanaman tumbuhan pakcoy.
        </p>
      </div>

      <div class="w-full border border-black/40 rounded-[20px] p-5 shadow-[2px_2px_12px_rgba(0,0,0,0.25)] relative mb-6">
        <h2 class="font-bold text-[20px] text-black text-center mb-2">Plants</h2>
        <p class="font-normal text-[12px] leading-[14px] text-justify text-black">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente, voluptas quaerat molestiae dolorem nulla debitis? Deskripsi tentang tanaman pakcoy, kadar ph air yang bagus untuk pakcoy antara a-z, range volume air yang dibutuhkan pada penanaman tumbuhan pakcoy.
        </p>
      </div>

      <div class="w-full border border-black/40 rounded-[20px] p-5 shadow-[2px_2px_12px_rgba(0,0,0,0.25)] relative mb-6">
        <h2 class="font-bold text-[20px] text-black text-center mb-2">Lettuce</h2>
        <p class="font-normal text-[12px] leading-[14px] text-justify text-black">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente, voluptas quaerat molestiae dolorem nulla debitis? Deskripsi tentang tanaman selada, kebutuhan sinar matahari dan nutrisi yang tepat.
        </p>
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
           <FileText :size="20" color="white" />
        </div>
        <span class="text-[10px] font-bold text-black">Info</span>
      </button>

      <button 
        @click="$emit('change-screen', 'set-sensor')"
        class="flex flex-col items-center justify-center w-14 opacity-70 hover:opacity-100 transition"
      >
        <div class="p-1.5 mb-0.5 relative">
           <PlusCircle :size="28" color="white" />
        </div>
        <span class="text-[10px] font-semibold text-white">Add</span>
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
  ArrowLeft, Search, Home, FileText, PlusCircle, Calculator 
} from 'lucide-vue-next';

defineEmits(['change-screen']);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
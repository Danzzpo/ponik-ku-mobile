<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden mx-auto font-sans flex flex-col transition-colors duration-300">
    
    <div class="w-full h-[268px] relative shrink-0">
      <button @click="$emit('change-screen', 'welcome')" class="absolute left-[21px] top-[33px] p-2 -ml-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition z-20">
         <ArrowLeft :size="24" class="text-black dark:text-white" />
      </button>

      <button @click="$emit('change-screen', 'login')" class="absolute left-[297px] top-[35px] font-bold text-[12px] text-black dark:text-white hover:text-green-600 transition z-20">
        Masuk
      </button>

      <h1 class="absolute left-[24px] top-[82px] font-bold text-[32px] text-black dark:text-white text-center">Daftar</h1>
      <p class="absolute left-[21px] top-[151px] w-[220px] font-normal text-[12px] text-black/60 dark:text-white/60">Buat akun Anda - nikmati layanan kami dengan fitur terbaru.</p>
    </div>

    <div class="w-full flex-1 bg-[#17941F] rounded-tl-[81px] rounded-none md:rounded-bl-[20px] md:rounded-br-[20px] shadow-[0_-10px_40px_rgba(0,0,0,0.1)] flex flex-col items-center pt-[60px] px-8 pb-10 overflow-y-auto scrollbar-hide">
      
      <div class="w-full space-y-4">
        <div>
          <label class="block text-white text-[14px] mb-2 ml-1">Nama Lengkap :</label>
          <div class="w-full h-[34px] bg-white dark:bg-gray-800 rounded-[20px] flex items-center px-4 transition-colors">
            <input type="text" class="w-full bg-transparent outline-none text-[14px] text-black dark:text-white"/>
          </div>
        </div>
        <div>
          <label class="block text-white text-[14px] mb-2 ml-1">E-mail :</label>
          <div class="w-full h-[34px] bg-white dark:bg-gray-800 rounded-[20px] flex items-center px-4 transition-colors">
            <input type="email" class="w-full bg-transparent outline-none text-[14px] text-black dark:text-white"/>
          </div>
        </div>
        <div>
          <label class="block text-white text-[14px] mb-2 ml-1">Kata Sandi :</label>
           <div class="w-full h-[34px] bg-white dark:bg-gray-800 rounded-[20px] flex items-center px-4 relative transition-colors">
            <input :type="showPass ? 'text' : 'password'" class="w-full bg-transparent outline-none text-[14px] text-black dark:text-white pr-8"/>
            <button @click="showPass = !showPass" class="absolute right-3 text-gray-400 hover:text-green-500"><Eye v-if="!showPass" :size="18"/><EyeOff v-else :size="18"/></button>
          </div>
        </div>
      </div>

      <button 
        @click="$emit('change-screen', 'verification')"
        class="w-[241px] h-[47px] bg-white dark:bg-gray-800 rounded-[20px] hover:bg-gray-100 dark:hover:bg-gray-700 transition active:scale-95 shadow-lg flex justify-center items-center group mt-10 shrink-0"
      >
        <span class="font-bold text-[14px] text-black dark:text-white group-hover:text-[#17941F] dark:group-hover:text-green-400 transition">Daftar</span>
      </button>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { ArrowLeft, Eye, EyeOff } from 'lucide-vue-next';
defineEmits(['change-screen']);
const showPass = ref(false);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
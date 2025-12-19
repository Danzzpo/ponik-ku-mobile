<template>
  <div class="w-full h-full md:w-[360px] md:h-[800px] bg-white md:rounded-[30px] shadow-2xl relative overflow-hidden ring-0 md:ring-8 ring-black mx-auto font-sans">
    
    <div class="absolute top-0 left-0 right-0 h-[268px] z-10 bg-white">
      
      <button 
        @click="$emit('change-screen', 'welcome')" 
        class="absolute left-[21px] top-[33px] p-2 -ml-2 hover:bg-gray-100 rounded-full transition z-20"
      >
         <ArrowLeft :size="24" color="black" />
      </button>

      <button 
        @click="$emit('change-screen', 'login')"
        class="absolute left-[297px] top-[35px] font-bold text-[12px] leading-[14px] text-black hover:text-green-600 transition z-20"
      >
        Masuk
      </button>

      <h1 class="absolute left-[24px] top-[82px] font-bold text-[32px] leading-[38px] text-black text-center">
        Daftar
      </h1>

      <p class="absolute left-[21px] top-[151px] w-[220px] font-normal text-[12px] leading-[14px] text-black opacity-60">
        Buat akun Anda - nikmati layanan kami dengan fitur terbaru.
      </p>

    </div>

    <div class="absolute top-[268px] bottom-0 left-0 right-0 bg-[#17941F] rounded-tl-[81px] rounded-none md:rounded-bl-[20px] md:rounded-br-[20px] shadow-[0_-10px_40px_rgba(0,0,0,0.1)] flex flex-col items-center overflow-y-auto scrollbar-hide pt-[60px] px-8 pb-10">
      
      <div class="w-full space-y-4">
        
        <div>
          <label class="block text-white text-[14px] font-normal mb-2 ml-1">Nama Lengkap :</label>
          <div class="w-full h-[34px] bg-white rounded-[20px] flex items-center px-4 shadow-sm">
            <input type="text" class="w-full bg-transparent outline-none font-medium text-[14px] text-black ml-1" />
          </div>
        </div>

        <div>
          <label class="block text-white text-[14px] font-normal mb-2 ml-1">E-mail :</label>
          <div class="w-full h-[34px] bg-white rounded-[20px] flex items-center px-4 shadow-sm">
            <input type="email" class="w-full bg-transparent outline-none font-medium text-[14px] text-black ml-1" />
          </div>
        </div>

        <div>
          <label class="block text-white text-[14px] font-normal mb-2 ml-1">Username :</label>
          <div class="w-full h-[34px] bg-white rounded-[20px] flex items-center px-4 shadow-sm">
            <input type="text" class="w-full bg-transparent outline-none font-medium text-[14px] text-black ml-1" />
          </div>
        </div>

        <div>
          <label class="block text-white text-[14px] font-normal mb-2 ml-1">Kata Sandi :</label>
          <div class="w-full h-[34px] bg-white rounded-[20px] flex items-center px-4 shadow-sm relative">
            <input 
              :type="showPass ? 'text' : 'password'" 
              class="w-full bg-transparent outline-none font-medium text-[14px] text-black ml-1 pr-8"
            />
            <button 
              @click="showPass = !showPass"
              class="absolute right-3 text-gray-400 hover:text-[#17941F] transition flex items-center justify-center"
              type="button"
            >
              <Eye v-if="!showPass" :size="18" />
              <EyeOff v-else :size="18" />
            </button>
          </div>
        </div>

      </div>

      <button 
        @click="$emit('change-screen', 'verification')"
        class="w-[241px] h-[47px] bg-white rounded-[20px] hover:bg-gray-100 transition active:scale-95 shadow-lg flex justify-center items-center group mt-10 shrink-0"
      >
        <span class="font-bold text-[14px] leading-[16px] text-black group-hover:text-[#17941F] transition">Daftar</span>
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
/* Hilangkan scrollbar */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}
.scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
}
</style>
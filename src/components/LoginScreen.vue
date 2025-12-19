<template>
  <div class="w-full h-screen md:w-[360px] md:h-[800px] bg-white md:rounded-[30px] shadow-2xl relative overflow-hidden ring-0 md:ring-8 ring-black mx-auto font-sans flex flex-col">
    
    <div class="w-full h-[268px] relative shrink-0">
      
      <button 
        @click="$emit('change-screen', 'welcome')" 
        class="absolute left-[21px] top-[33px] p-2 -ml-2 hover:bg-gray-100 rounded-full transition z-20"
      >
         <ArrowLeft :size="24" color="black" />
      </button>

      <button 
        @click="$emit('change-screen', 'register')"
        class="absolute left-[297px] top-[35px] font-bold text-[12px] leading-[14px] text-black hover:text-green-600 transition z-20"
      >
        Daftar
      </button>

      <h1 class="absolute left-[18px] top-[90px] font-bold text-[32px] leading-[38px] text-black text-center">
        Masuk
      </h1>

      <p class="absolute left-[18px] top-[146px] w-[220px] font-normal text-[12px] leading-[14px] text-black opacity-60">
        Masuk ke akun Anda - nikmati fitur eksklusif dan banyak lagi.
      </p>

    </div>

    <div class="w-full flex-1 bg-[#17941F] rounded-tl-[81px] rounded-tr-[0px] md:rounded-bl-[20px] md:rounded-br-[20px] shadow-[0_-10px_40px_rgba(0,0,0,0.1)] flex flex-col items-center pt-[80px] px-8 space-y-6 overflow-y-auto scrollbar-hide">
      
      <div class="w-full h-[45px] bg-white rounded-[20px] flex items-center px-4 shadow-sm shrink-0">
        <input 
          type="text" 
          placeholder="Username/Email"
          class="w-full bg-transparent outline-none font-medium text-[14px] leading-[16px] text-black placeholder:text-black/40 ml-1"
        />
      </div>

      <div class="w-full h-[45px] bg-white rounded-[20px] flex items-center px-4 shadow-sm relative shrink-0">
        <input 
          :type="showPass ? 'text' : 'password'" 
          placeholder="Kata Sandi"
          class="w-full bg-transparent outline-none font-medium text-[14px] leading-[16px] text-black placeholder:text-black/40 ml-1 pr-8"
        />
        <button 
          @click="showPass = !showPass"
          class="absolute right-4 text-gray-400 hover:text-[#17941F] transition flex items-center justify-center"
          type="button"
        >
          <Eye v-if="!showPass" :size="20" />
          <EyeOff v-else :size="20" />
        </button>
      </div>

      <div class="w-full flex justify-end -mt-2">
        <button class="font-medium text-[12px] leading-[14px] text-white hover:underline hover:text-green-100 transition">
          Lupa Kata Sandi?
        </button>
      </div>

      <button 
        @click="handleLogin"
        class="w-full h-[47px] bg-white rounded-[20px] hover:bg-gray-100 transition active:scale-95 shadow-lg flex justify-center items-center group shrink-0 mb-10"
      >
        <span class="font-bold text-[14px] leading-[16px] text-black/90 group-hover:text-[#17941F] transition">Masuk</span>
      </button>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue';
import { ArrowLeft, Eye, EyeOff } from 'lucide-vue-next';

const emit = defineEmits(['change-screen']);
const showPass = ref(false);

const handleLogin = () => {
  alert("Sedang Masuk...");
};
</script>

<style scoped>
/* Sembunyikan scrollbar tapi tetap bisa scroll */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}
.scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
}
</style>
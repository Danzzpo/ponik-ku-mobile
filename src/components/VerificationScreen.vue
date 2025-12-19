<template>
  <div class="w-full h-full md:w-[360px] md:h-[800px] bg-white md:rounded-[30px] shadow-2xl relative overflow-hidden ring-0 md:ring-8 ring-black mx-auto font-sans">
    
    <button 
      @click="$emit('change-screen', 'register')" 
      class="absolute left-[21px] top-[33px] p-2 -ml-2 hover:bg-gray-100 rounded-full transition z-20"
    >
       <ArrowLeft :size="24" color="black" />
    </button>

    <h1 class="absolute left-[16px] top-[153px] w-full pr-8 font-medium text-[20px] leading-[23px] text-black text-left">
      Masukkan kode verifikasi
    </h1>

    <p class="absolute left-[16px] top-[200px] w-[328px] font-medium text-[12px] leading-[14px] text-black">
      Kami baru saja mengirimkan kode autentikasi via email ke <span class="font-bold">mic********@gmail.com</span>. Tidak menerima email? Cek folder spam atau junk Anda.
    </p>

    <div class="absolute left-[27px] top-[266px] w-[298px] h-[49px] border border-black rounded-[10px] flex items-center justify-center">
      <input 
        type="text" 
        placeholder="Kode verifikasi (6 angka)" 
        class="w-full h-full bg-transparent text-center font-medium text-[14px] text-black outline-none placeholder:text-black/47 rounded-[10px]"
      />
    </div>

    <button 
      @click="handleVerify"
      class="absolute left-[59px] top-[339px] w-[241px] h-[47px] bg-[#17941F] rounded-[20px] hover:bg-[#137a1a] transition active:scale-95 shadow-md flex items-center justify-center text-white font-medium text-[14px]"
    >
      Verifikasi
    </button>

    <div class="absolute left-[16px] top-[412px] flex items-center cursor-pointer" @click="rememberMe = !rememberMe">
      <div 
        class="w-[13px] h-[12px] border border-black flex items-center justify-center mr-2 transition"
        :class="{'bg-black': rememberMe}"
      >
        <Check v-if="rememberMe" :size="10" color="white" />
      </div>
      
      <span class="font-medium text-[12px] leading-[14px] text-black select-none">
        Jangan tanya lagi di perangkat ini
      </span>
    </div>

    <button class="absolute left-[33px] top-[438px] font-medium text-[12px] leading-[14px] text-[#5D4FFA] hover:underline">
      Kirim ulang kode
    </button>

  </div>
</template>

<script setup>
import { ref } from 'vue';
import { ArrowLeft, Check } from 'lucide-vue-next';

const emit = defineEmits(['change-screen']);
const rememberMe = ref(false);

const handleVerify = () => {
  // Simulasi Verifikasi berhasil
  alert("Verifikasi Berhasil!");
  emit('change-screen', 'login'); // Balik ke login atau masuk dashboard
};
</script>
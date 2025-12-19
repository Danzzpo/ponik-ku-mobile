<template>
  <div class="w-full h-full bg-white relative overflow-hidden mx-auto font-sans flex flex-col">
    
    <button @click="$emit('change-screen', 'register')" class="absolute left-[21px] top-[33px] p-2 -ml-2 hover:bg-gray-100 rounded-full transition z-20">
       <ArrowLeft :size="24" color="black" />
    </button>

    <h1 class="absolute left-[16px] top-[153px] w-full pr-8 font-medium text-[20px] text-black">Masukkan kode verifikasi</h1>
    <p class="absolute left-[16px] top-[200px] w-[328px] font-medium text-[12px] text-black">Kami baru saja mengirimkan kode autentikasi via email.</p>

    <div class="absolute left-[27px] top-[266px] w-[298px] h-[49px] border border-black rounded-[10px] flex items-center justify-center">
      <input type="text" placeholder="Kode 6 angka" class="w-full h-full bg-transparent text-center font-medium text-[14px] outline-none"/>
    </div>

    <button @click="handleVerify" class="absolute left-[59px] top-[339px] w-[241px] h-[47px] bg-[#17941F] rounded-[20px] text-white font-medium text-[14px] flex items-center justify-center shadow-md active:scale-95 transition">
      Verifikasi
    </button>
    
    <button class="absolute left-[33px] top-[438px] font-medium text-[12px] text-[#5D4FFA]">Kirim ulang kode</button>

  </div>
</template>

<script setup>
import { ArrowLeft } from 'lucide-vue-next';
const emit = defineEmits(['change-screen']);

const handleVerify = () => {
  // Langsung ke Home
  emit('change-screen', 'home');
};
</script>
<template>
  <div class="w-[360px] h-[800px] bg-white rounded-[20px] shadow-2xl relative overflow-hidden ring-8 ring-black rounded-[30px] mx-auto">
    
    <img src="/logo.png" alt="Logo" class="absolute left-[115px] top-[174px] w-[130px] h-[185px] object-contain" />

    <div class="absolute left-0 top-[450px] w-[360px] h-[350px] bg-[#17941F] rounded-tl-[58px] rounded-bl-[20px] rounded-br-[20px] shadow-[2px_2px_20px_rgba(0,0,0,0.25)]">
      
      <h1 class="absolute left-[25px] top-[50px] font-medium text-[32px] leading-[38px] text-white">Selamat Datang</h1>
      
      <p class="absolute left-[26px] top-[100px] w-[300px] font-medium text-[14px] leading-[22px] text-white opacity-90">
        Wujudkan hasil panen terbaik dengan teknologi hidroponik pintar dalam genggaman Anda.
      </p>

      <button @click="$emit('change-screen', 'login')" class="absolute left-[54px] top-[190px] w-[109px] h-[47px] bg-white rounded-[20px] flex items-center justify-center hover:bg-gray-100 transition active:scale-95 shadow-md">
        <span class="font-bold text-[15px] leading-[18px] text-black">Masuk</span>
      </button>

      <button @click="$emit('change-screen', 'register')" class="absolute left-[179px] top-[190px] w-[109px] h-[47px] bg-white rounded-[20px] flex items-center justify-center hover:bg-gray-100 transition active:scale-95 shadow-md">
        <span class="font-bold text-[15px] leading-[18px] text-black">Daftar</span>
      </button>

    </div>
  </div>
</template>

<script setup>
defineEmits(['change-screen']);
</script>
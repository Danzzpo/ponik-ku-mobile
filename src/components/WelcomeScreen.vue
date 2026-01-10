<template>
  <div class="w-full h-full bg-white relative overflow-hidden font-sans">
    
    <img 
      src="/logo.png" 
      alt="Logo" 
      class="absolute left-1/2 top-[20%] -translate-x-1/2 w-[140px] h-auto object-contain drop-shadow-lg" 
    />

    <div class="absolute left-0 bottom-0 w-full h-[400px] bg-[#17941F] rounded-tl-[60px] rounded-tr-none shadow-[0_-10px_30px_rgba(0,0,0,0.15)]">
      
      <h1 class="absolute left-[30px] top-[50px] font-bold text-[32px] leading-[1.2] text-white">
        Selamat Datang
      </h1>
      
      <p class="absolute left-[30px] top-[100px] right-[30px] font-medium text-[14px] leading-[1.6] text-white/90">
        Wujudkan hasil panen terbaik dengan teknologi hidroponik pintar dalam genggaman Anda.
      </p>

      <div class="absolute top-[180px] w-full px-[30px] flex justify-between gap-4">
        <button 
          @click="$emit('change-screen', 'login')" 
          class="flex-1 h-[50px] bg-white rounded-[20px] flex items-center justify-center hover:bg-gray-100 transition active:scale-95 shadow-lg text-[#17941F]"
        >
          <span class="font-bold text-[16px]">Masuk</span>
        </button>

        <button 
          @click="$emit('change-screen', 'register')" 
          class="flex-1 h-[50px] bg-[#137a1a] border border-white/30 rounded-[20px] flex items-center justify-center hover:bg-[#0f6315] transition active:scale-95 shadow-lg text-white"
        >
          <span class="font-bold text-[16px]">Daftar</span>
        </button>
      </div>

      <div class="absolute bottom-[40px] left-0 w-full px-[30px] text-center">
        <p class="text-[11px] text-white/80 italic leading-tight bg-black/10 p-2 rounded-lg border border-white/10">
          <span class="font-bold text-yellow-300">NB:</span> Karena ini hanya prototype, 
          silakan langsung masuk menggunakan nickname dan password bebas.
        </p>
      </div>

    </div>
  </div>
</template>

<script setup>
defineEmits(['change-screen']);
</script>
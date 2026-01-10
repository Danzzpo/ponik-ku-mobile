<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden font-sans transition-colors duration-300">
    
    <img 
      src="/logo.png" 
      alt="Logo" 
      class="absolute left-1/2 top-[20%] -translate-x-1/2 w-[140px] h-auto object-contain drop-shadow-lg" 
    />

    <div class="absolute left-0 bottom-0 w-full h-[400px] bg-[#17941F] rounded-tl-[60px] rounded-tr-none shadow-[0_-10px_30px_rgba(0,0,0,0.15)] dark:shadow-none transition-colors duration-300">
      
      <h1 class="absolute left-[30px] top-[50px] font-bold text-[32px] leading-[1.2] text-white">
        Selamat Datang
      </h1>
      
      <p class="absolute left-[30px] top-[100px] right-[30px] font-medium text-[14px] leading-[1.6] text-white/90">
        Wujudkan hasil panen terbaik dengan teknologi hidroponik pintar dalam genggaman Anda.
      </p>

      <div class="absolute top-[180px] w-full px-[30px] flex justify-between gap-4">
        
        <button 
          @click="$emit('change-screen', 'login')" 
          class="flex-1 h-[50px] rounded-[20px] flex items-center justify-center shadow-lg transition active:scale-95 
                 bg-white text-[#17941F] hover:bg-gray-100 
                 dark:bg-gray-800 dark:text-green-400 dark:hover:bg-gray-700 dark:border dark:border-white/10"
        >
          <span class="font-bold text-[16px]">Masuk</span>
        </button>

        <button 
          @click="$emit('change-screen', 'register')" 
          class="flex-1 h-[50px] rounded-[20px] flex items-center justify-center shadow-lg transition active:scale-95 
                 bg-white text-[#17941F] hover:bg-gray-100 
                 dark:bg-gray-800 dark:text-green-400 dark:hover:bg-gray-700 dark:border dark:border-white/10"
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
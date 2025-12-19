<template>
  <div class="min-h-screen bg-gray-50 flex justify-center items-center font-sans p-4 overflow-hidden">
    
    <div class="relative w-[360px] h-[800px] bg-white rounded-[30px] shadow-2xl ring-8 ring-black overflow-hidden isolate">
      
      <SplashScreen 
        v-if="screen === 'splash'" 
        @finish="screen = 'welcome'" 
        class="absolute inset-0 z-50"
      />

      <WelcomeScreen 
        v-if="screen === 'welcome'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-10" 
      />

      <Transition name="slide-left">
        <LoginScreen 
          v-if="screen === 'login'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20" 
        />
      </Transition>

      <Transition name="slide-left">
        <div v-if="screen === 'register'" class="absolute inset-0 z-20 w-full h-full bg-white flex flex-col justify-center items-center">
            <button @click="screen = 'welcome'" class="absolute top-10 left-6 p-2 hover:bg-gray-100 rounded-full transition">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m12 19-7-7 7-7"/><path d="M19 12H5"/></svg>
            </button>
            <h1 class="text-2xl font-bold text-green-700">Halaman Register</h1>
            <p class="text-gray-500 mt-2">Masih dalam pengembangan</p>
        </div>
      </Transition>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import SplashScreen from './components/SplashScreen.vue'; 
import WelcomeScreen from './components/WelcomeScreen.vue';
import LoginScreen from './components/LoginScreen.vue';

const screen = ref('splash');

const changeScreen = (targetScreen) => {
  screen.value = targetScreen;
};
</script>

<style>
/* ANIMASI SLIDE DARI KIRI (CLEAN)
   Tidak ada efek zoom/scale, murni geser.
*/

.slide-left-enter-active,
.slide-left-leave-active {
  /* Durasi 0.5 detik dengan kurva halus */
  transition: transform 0.5s cubic-bezier(0.25, 1, 0.5, 1);
}

/* POSISI AWAL MASUK (Dari Kiri Luar Layar) */
.slide-left-enter-from {
  transform: translateX(-100%);
}

/* POSISI AKHIR (Normal di Tengah) */
.slide-left-enter-to {
  transform: translateX(0);
}

/* SAAT KELUAR (Geser Balik ke Kiri) */
.slide-left-leave-to {
  transform: translateX(-100%);
  z-index: 30; /* Tetap di atas saat keluar */
}
</style>
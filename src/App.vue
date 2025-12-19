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

      <Transition name="slide-side">
        <LoginScreen 
          v-if="screen === 'login'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white" 
        />
      </Transition>

      <Transition name="slide-side">
        <RegisterScreen 
          v-if="screen === 'register'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white"
        />
      </Transition>

      <Transition name="slide-side">
        <VerificationScreen 
          v-if="screen === 'verification'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white"
        />
      </Transition>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import SplashScreen from './components/SplashScreen.vue'; 
import WelcomeScreen from './components/WelcomeScreen.vue';
import LoginScreen from './components/LoginScreen.vue';
import RegisterScreen from './components/RegisterScreen.vue';
import VerificationScreen from './components/VerificationScreen.vue'; // Import komponen baru
const screen = ref('splash');

// Fungsi ganti layar sederhana
const changeScreen = (targetScreen) => {
  screen.value = targetScreen;
};
</script>

<style>
/* ========================================= */
/* ANIMASI SERAGAM (Slide Side)              */
/* Semua halaman masuk dari KIRI ke KANAN    */
/* ========================================= */

.slide-side-enter-active,
.slide-side-leave-active {
  /* Durasi 0.5 detik, gerakan luwes (cubic-bezier) */
  transition: transform 0.5s cubic-bezier(0.25, 1, 0.5, 1);
}

/* SAAT MASUK: */
/* Mulai dari luar layar sebelah KIRI (-100%) */
.slide-side-enter-from {
  transform: translateX(-100%);
  z-index: 30; /* Pastikan dia menimpa halaman Welcome */
}

/* Berakhir di TENGAH (0) */
.slide-side-enter-to {
  transform: translateX(0);
}

/* SAAT KELUAR (TOMBOL BACK): */
/* Balik lagi ke KIRI (-100%) */
.slide-side-leave-to {
  transform: translateX(-100%);
  z-index: 30;
}
</style>
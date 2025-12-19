<template>
  <div class="min-h-screen bg-gray-50 flex justify-center items-center font-sans p-4 overflow-hidden">
    <div class="relative w-[360px] h-[800px] bg-white rounded-[30px] shadow-2xl ring-8 ring-black overflow-hidden isolate">
      
      <SplashScreen 
        v-if="screen === 'splash'" 
        @finish="screen = 'welcome'" 
        class="absolute inset-0 z-50 bg-white" 
      />

      <WelcomeScreen 
        v-if="screen === 'welcome'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-10 bg-white" 
      />

      <LoginScreen 
        v-if="screen === 'login'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white" 
      />

      <RegisterScreen 
        v-if="screen === 'register'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white"
      />

      <VerificationScreen 
        v-if="screen === 'verification'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white"
      />

      <HomeScreen 
        v-if="screen === 'home'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white" 
      />

      <Transition name="slide-side"></Transition>
      <SetSensorScreen 
        v-if="screen === 'set-sensor'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white"
      />
      <transition name="slide-side">
         <dashboard-screen 
        v-if="screen === 'dashboard'" 
        @change-screen="changeScreen" 
        class="absolute inset-0 z-20 bg-white"
      />
      </transition>
      
      <Transition name="slide-side">
        <PaymentScreen 
          v-if="screen === 'payment'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-30 bg-white" 
        />
      </Transition>
    </div>
</div>
</template>

<script setup>
import { ref } from 'vue';
// Import Semua Component
import SplashScreen from './components/SplashScreen.vue'; 
import WelcomeScreen from './components/WelcomeScreen.vue';
import LoginScreen from './components/LoginScreen.vue';
import RegisterScreen from './components/RegisterScreen.vue';
import VerificationScreen from './components/VerificationScreen.vue';
import HomeScreen from './components/HomeScreen.vue'; 
import SetSensorScreen from './components/SetSensorScreen.vue';
import DashboardScreen from './components/DashboardScreen.vue';
import PaymentScreen from './components/PaymentScreen.vue';
const screen = ref('splash');

// Fungsi ganti layar sederhana (Langsung ubah value)
const changeScreen = (targetScreen) => {
  screen.value = targetScreen;
};
</script>

<style>
/* TIDAK ADA CSS ANIMASI SAMA SEKALI */
/* Layar akan berganti instan */
</style>
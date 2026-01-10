<template>
  <div class="w-full h-full bg-gray-50 overflow-hidden block md:flex md:justify-center md:items-center md:p-4">
    
    <div class="fixed inset-0 w-full h-full md:relative md:w-[360px] md:h-[800px] bg-white md:rounded-[30px] shadow-none md:shadow-2xl ring-0 md:ring-8 ring-black overflow-hidden isolate z-0">
      
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

      <Transition name="slide-side">
        <SetSensorScreen 
          v-if="screen === 'set-sensor'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white"
        />
      </Transition>

      <Transition name="slide-side">
         <DashboardScreen 
          v-if="screen === 'dashboard'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white"
        />
      </Transition>
      
      <Transition name="slide-side">
        <PaymentScreen 
          v-if="screen === 'payment'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-30 bg-white" 
        />
      </Transition>

      <Transition name="fade">
        <InfoScreen 
          v-if="screen === 'info'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white" 
        />
      </Transition>

      <Transition name="fade">
        <InfoDetailScreen 
          v-if="screen === 'info-detail'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-30 bg-white" 
        />
      </Transition>

      <Transition name="slide-side">
        <CalculatorScreen 
          v-if="screen === 'calculator'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white" 
        />
      </Transition>

      <Transition name="fade">
        <AddDeviceScreen 
          v-if="screen === 'add-device'" 
          @change-screen="changeScreen" 
          class="absolute inset-0 z-20 bg-white" 
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
import InfoScreen from './components/InfoScreen.vue';
import InfoDetailScreen from './components/InfoDetailScreen.vue';
import CalculatorScreen from './components/CalculatorScreen.vue';
import AddDeviceScreen from './components/AddDeviceScreen.vue';

const screen = ref('splash');

const changeScreen = (targetScreen) => {
  screen.value = targetScreen;
};
</script>

<style>
/* CSS Animasi Transisi */
.slide-side-enter-active,
.slide-side-leave-active {
  transition: transform 0.3s ease;
}

.slide-side-enter-from {
  transform: translateX(100%);
}

.slide-side-leave-to {
  transform: translateX(-100%);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
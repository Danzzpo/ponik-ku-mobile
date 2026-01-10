<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden flex flex-col transition-colors duration-300">
    
    <div class="w-full h-[70px] flex items-center px-4 shrink-0 border-b border-gray-100 dark:border-gray-800 bg-white dark:bg-gray-900 transition-colors duration-300 z-20">
      <button @click="$emit('change-screen', 'dashboard')" class="p-2 -ml-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition">
         <ArrowLeft :size="24" class="text-black dark:text-white" />
      </button>
      <h1 class="font-bold text-[20px] text-black dark:text-white ml-4">Settings</h1>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 py-6">
      
      <h2 class="font-bold text-[14px] text-gray-500 dark:text-gray-400 uppercase tracking-wider mb-4">General</h2>
      
      <div class="flex items-center justify-between mb-6">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-blue-50 dark:bg-blue-900/20 rounded-full flex items-center justify-center">
            <Bell :size="20" class="text-blue-600 dark:text-blue-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Notifications</span>
        </div>
        <button class="w-[50px] h-[26px] bg-[#17941F] rounded-full relative">
          <div class="absolute top-[3px] left-[27px] w-[20px] h-[20px] bg-white rounded-full shadow-sm"></div>
        </button>
      </div>

      <div class="flex items-center justify-between mb-6">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-purple-50 dark:bg-purple-900/20 rounded-full flex items-center justify-center">
            <Moon :size="20" class="text-purple-600 dark:text-purple-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Dark Mode</span>
        </div>
        
        <button 
          @click="toggleDarkMode"
          class="w-[50px] h-[26px] rounded-full relative transition-colors duration-300 focus:outline-none"
          :class="isDark ? 'bg-[#17941F]' : 'bg-gray-300 dark:bg-gray-700'"
        >
          <div 
            class="absolute top-[3px] w-[20px] h-[20px] bg-white rounded-full shadow-sm transition-all duration-300 flex items-center justify-center"
            :class="isDark ? 'left-[27px]' : 'left-[3px]'"
          >
             <Moon v-if="isDark" :size="12" class="text-[#17941F]" />
          </div>
        </button>
      </div>

      <button class="w-full flex items-center justify-between mb-6 group">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-orange-50 dark:bg-orange-900/20 rounded-full flex items-center justify-center">
            <Globe :size="20" class="text-orange-600 dark:text-orange-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Language</span>
        </div>
        <div class="flex items-center text-gray-400 group-hover:text-[#17941F] transition">
          <span class="text-[14px] mr-2">English</span>
          <ChevronRight :size="20" />
        </div>
      </button>

      <div class="w-full h-[1px] bg-gray-100 dark:bg-gray-800 mb-6"></div>

      <h2 class="font-bold text-[14px] text-gray-500 dark:text-gray-400 uppercase tracking-wider mb-4">Security</h2>

      <button class="w-full flex items-center justify-between mb-6 group">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-red-50 dark:bg-red-900/20 rounded-full flex items-center justify-center">
            <Lock :size="20" class="text-red-600 dark:text-red-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Change Password</span>
        </div>
        <ChevronRight :size="20" class="text-gray-400 group-hover:text-[#17941F] transition" />
      </button>

      <button class="w-full flex items-center justify-between mb-6 group">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-green-50 dark:bg-green-900/20 rounded-full flex items-center justify-center">
            <ShieldCheck :size="20" class="text-green-600 dark:text-green-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Privacy Policy</span>
        </div>
        <ChevronRight :size="20" class="text-gray-400 group-hover:text-[#17941F] transition" />
      </button>

      <div class="w-full h-[1px] bg-gray-100 dark:bg-gray-800 mb-6"></div>

      <h2 class="font-bold text-[14px] text-gray-500 dark:text-gray-400 uppercase tracking-wider mb-4">About</h2>
      
      <button class="w-full flex items-center justify-between mb-6 group">
        <div class="flex items-center">
          <div class="w-[40px] h-[40px] bg-gray-100 dark:bg-gray-800 rounded-full flex items-center justify-center">
            <Info :size="20" class="text-gray-600 dark:text-gray-400" />
          </div>
          <span class="font-medium text-[16px] text-black dark:text-white ml-4">Version</span>
        </div>
        <span class="text-[14px] text-gray-400">v1.0.2</span>
      </button>

      </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { 
  ArrowLeft, Bell, Moon, Globe, ChevronRight, 
  Lock, ShieldCheck, Info 
} from 'lucide-vue-next';

defineEmits(['change-screen']);

const isDark = ref(false);

const toggleDarkMode = () => {
  isDark.value = !isDark.value;
  if (isDark.value) {
    document.documentElement.classList.add('dark');
    localStorage.setItem('theme', 'dark');
  } else {
    document.documentElement.classList.remove('dark');
    localStorage.setItem('theme', 'light');
  }
};

onMounted(() => {
  if (document.documentElement.classList.contains('dark')) {
    isDark.value = true;
  }
});
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
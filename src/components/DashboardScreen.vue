<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden mx-auto font-sans flex flex-col transition-colors duration-300">
    
    <div class="w-full h-[70px] flex items-center px-4 shrink-0 border-b border-gray-100 dark:border-gray-800">
      <button @click="$emit('change-screen', 'home')" class="p-2 -ml-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition">
         <ArrowLeft :size="24" class="text-black dark:text-white" />
      </button>
      <h1 class="font-bold text-[20px] text-black dark:text-white ml-4">Dashboard</h1>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 py-6">
      
      <div class="w-full h-[80px] border border-black/25 dark:border-white/20 rounded-[15px] flex items-center px-4 relative mb-8 shadow-sm">
        <div class="w-[50px] h-[50px] rounded-full border border-black/80 dark:border-white/50 flex items-center justify-center">
          <User :size="30" class="text-black/80 dark:text-white/80" />
        </div>
        <div class="ml-4 flex flex-col justify-center">
          <span class="font-bold text-[15px] text-black dark:text-white leading-tight">Nugroho Gajah</span>
          <span class="font-medium text-[13px] text-black/40 dark:text-white/40 mt-1">mit.shuki23@gmail.com</span>
        </div>
        <button class="absolute right-4 top-1/2 -translate-y-1/2 p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition">
          <Edit2 :size="20" class="text-[#33363F] dark:text-white" />
        </button>
      </div>

      <div class="space-y-1 mb-6">
        
        <button class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <UserCog :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Manage Account</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button @click="$emit('change-screen', 'set-sensor')" class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <Eye :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Set Sensor</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <ShoppingBag :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Property</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button @click="$emit('change-screen', 'payment')" class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <CreditCard :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Payment & Subscription</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button @click="$emit('change-screen', 'setting')" class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <Settings :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Setting</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <HelpCircle :size="24" class="text-[#33363F] dark:text-gray-300" />
            <span class="font-medium text-[15px] text-black dark:text-white ml-4">Help & Feedback</span>
          </div>
          <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

        <button @click="$emit('change-screen', 'login')" class="w-full h-[50px] flex items-center justify-between group">
          <div class="flex items-center">
            <LogOut :size="24" class="text-black dark:text-white" />
            <span class="font-medium text-[17px] text-black dark:text-white ml-4">Log out</span>
          </div>
        </button>
        <div class="h-[1px] w-full bg-black/10 dark:bg-white/10"></div>

      </div>

      <div class="mt-8 space-y-4">
        <div class="flex items-center space-x-4">
          <div class="w-full h-[1px] bg-black/10 dark:bg-white/10"></div>
          <span class="text-[15px] font-medium text-black dark:text-white">Information</span>
          <div class="w-full h-[1px] bg-black/10 dark:bg-white/10"></div>
        </div>

        <button class="w-full flex items-center justify-between py-2 group">
           <div class="flex items-center">
             <Info :size="24" class="text-[#33363F] dark:text-gray-300" />
             <span class="font-medium text-[15px] text-black dark:text-white ml-4">About</span>
           </div>
           <ChevronRight :size="24" class="text-[#7FB77E] opacity-0 group-hover:opacity-100 transition" />
        </button>
      </div>

    </div>
  </div>
</template>

<script setup>
import { 
  ArrowLeft, User, Edit2, ChevronRight, UserCog, Eye, 
  ShoppingBag, CreditCard, Settings, HelpCircle, LogOut, Info, Star 
} from 'lucide-vue-next';

defineEmits(['change-screen']);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
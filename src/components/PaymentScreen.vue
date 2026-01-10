<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden mx-auto font-sans flex flex-col transition-colors duration-300">
    
    <div class="w-full h-[70px] flex items-center px-4 shrink-0 bg-white dark:bg-gray-900 border-b border-gray-300 dark:border-gray-800 relative z-10 transition-colors">
      <button 
        @click="$emit('change-screen', 'dashboard')" 
        class="p-2 -ml-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition"
      >
         <ArrowLeft :size="24" class="text-black dark:text-white" />
      </button>
      <h1 class="font-bold text-[20px] text-black dark:text-white ml-4">Pembayaran</h1>
    </div>

    <div class="flex-1 overflow-y-auto scrollbar-hide px-6 py-6">
      
      <div class="w-full h-[140px] bg-gradient-to-r from-[#17941F] to-[#25D366] rounded-[20px] shadow-lg p-5 text-white relative overflow-hidden mb-8">
        <div class="absolute -right-4 -bottom-8 text-white opacity-10">
           <CreditCard :size="120" />
        </div>

        <div class="relative z-10">
          <div class="flex justify-between items-start">
            <div>
              <p class="text-[12px] opacity-80 font-medium">Paket Saat Ini</p>
              <h2 class="text-[24px] font-bold">Premium Pro</h2>
            </div>
            <div class="bg-white/20 p-2 rounded-full">
              <CheckCircle :size="20" color="white" />
            </div>
          </div>
          
          <div class="mt-6 flex justify-between items-end">
            <div>
               <p class="text-[12px] opacity-80">Berlaku hingga</p>
               <p class="text-[14px] font-bold">20 Des 2025</p>
            </div>
            <button class="bg-white text-[#17941F] px-4 py-1.5 rounded-[10px] text-[12px] font-bold hover:bg-gray-100 transition shadow-sm">
              Perpanjang
            </button>
          </div>
        </div>
      </div>

      <div class="mb-6">
        <h3 class="font-bold text-[16px] text-black dark:text-white mb-3">Metode Pembayaran</h3>
        
        <div class="w-full h-[60px] border border-gray-200 dark:border-gray-700 rounded-[15px] flex items-center px-4 justify-between mb-3 hover:border-[#17941F] transition cursor-pointer group">
           <div class="flex items-center">
             <div class="w-[36px] h-[36px] bg-blue-50 dark:bg-blue-900/20 rounded-full flex items-center justify-center text-blue-600 dark:text-blue-400">
                <CreditCard :size="20" />
             </div>
             <div class="ml-3">
               <p class="text-[14px] font-bold text-black dark:text-white">Visa •••• 4242</p>
               <p class="text-[10px] text-gray-400">Kedaluwarsa 09/28</p>
             </div>
           </div>
           <div class="w-4 h-4 rounded-full border border-gray-300 dark:border-gray-600 group-hover:border-[#17941F] group-hover:bg-[#17941F]"></div>
        </div>

        <button class="w-full h-[50px] border border-dashed border-gray-300 dark:border-gray-600 rounded-[15px] flex items-center justify-center text-gray-500 dark:text-gray-400 hover:text-[#17941F] dark:hover:text-green-400 hover:border-[#17941F] transition">
           <Plus :size="18" class="mr-2" />
           <span class="text-[13px] font-medium">Tambah Metode Baru</span>
        </button>
      </div>

      <div>
        <h3 class="font-bold text-[16px] text-black dark:text-white mb-3">Riwayat Transaksi</h3>
        
        <div class="space-y-4">
          <div class="flex items-center justify-between">
             <div class="flex items-center">
               <div class="w-[40px] h-[40px] bg-gray-100 dark:bg-gray-800 rounded-[10px] flex items-center justify-center text-black/60 dark:text-white/60">
                 <Receipt :size="20" />
               </div>
               <div class="ml-3">
                 <p class="text-[14px] font-bold text-black dark:text-white">Langganan Bulanan</p>
                 <p class="text-[11px] text-gray-400">19 Des 2024 • 09:41</p>
               </div>
             </div>
             <span class="text-[14px] font-bold text-red-500">-Rp 50.000</span>
          </div>

          <div class="flex items-center justify-between">
             <div class="flex items-center">
               <div class="w-[40px] h-[40px] bg-gray-100 dark:bg-gray-800 rounded-[10px] flex items-center justify-center text-black/60 dark:text-white/60">
                 <Receipt :size="20" />
               </div>
               <div class="ml-3">
                 <p class="text-[14px] font-bold text-black dark:text-white">Beli Alat Sensor</p>
                 <p class="text-[11px] text-gray-400">10 Nov 2024 • 14:20</p>
               </div>
             </div>
             <span class="text-[14px] font-bold text-red-500">-Rp 120.000</span>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { 
  ArrowLeft, CreditCard, CheckCircle, 
  Plus, Receipt 
} from 'lucide-vue-next';

defineEmits(['change-screen']);
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar { display: none; }
.scrollbar-hide { -ms-overflow-style: none; scrollbar-width: none; }
</style>
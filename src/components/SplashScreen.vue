<template>
  <div class="w-[360px] h-[800px] bg-white rounded-[20px] shadow-2xl relative overflow-hidden ring-8 ring-black rounded-[30px] mx-auto flex flex-col items-center">
    
    <Transition name="smooth-logo" appear>
      
      <img 
        src="/logo.png" 
        alt="Logo Ponik-ku" 
        class="absolute left-[114px] top-[177px] w-[130px] h-[185px] object-contain drop-shadow-xl"
      />

    </Transition>

  </div>
</template>

<script setup>
import { onMounted } from 'vue';

const emit = defineEmits(['finish']);

onMounted(() => {
  setTimeout(() => {
    emit('finish');
  }, 3000);
});
</script>

<style scoped>
/* Animasi Logo Muncul Perlahan */
.smooth-logo-enter-active {
  transition: all 1.5s cubic-bezier(0.22, 1, 0.36, 1);
}
.smooth-logo-enter-from {
  opacity: 0;
  transform: translateY(50px) scale(0.9);
}
.smooth-logo-enter-to {
  opacity: 1;
  transform: translateY(0) scale(1);
}
</style>
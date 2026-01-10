<template>
  <div class="w-full h-full bg-white dark:bg-gray-900 relative overflow-hidden flex flex-col items-center transition-colors duration-300">
    
    <Transition name="smooth-logo" appear>
      <img 
        src="/logo.png" 
        alt="Logo Ponik-ku" 
        class="absolute left-1/2 top-[25%] -translate-x-1/2 w-[130px] h-[185px] object-contain drop-shadow-xl"
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
.smooth-logo-enter-active {
  transition: all 1.5s cubic-bezier(0.22, 1, 0.36, 1);
}
.smooth-logo-enter-from {
  opacity: 0;
  transform: translate(-50%, 50px) scale(0.9);
}
.smooth-logo-enter-to {
  opacity: 1;
  transform: translate(-50%, 0) scale(1);
}
</style>
<template>
    <div :class="['absolute top-0 left-0 h-screen w-screen bg-[#0a0606] transform transition-transform duration-300 ease-in-out filter drop-shadow-md', open ? '-translate-y-0' : '-translate-y-full']">
      <div class="flex flex-col items-center justify-center gap-y-6 py-10 text-lg text-black">
          <p class="hover:text-orange-400 text-white transition-all duration-300" to="/" @click="setOpen(false)">Home</p>
          <p class="hover:text-orange-400 text-white transition-all duration-300" to="/about" @click="setOpen(false)">About Us</p>
          <p class="hover:text-orange-400 text-white transition-all duration-300" to="/portfolio" @click="setOpen(false)">Portfolio</p>
          <p class="hover:text-orange-400 text-white transition-all duration-300" to="/news" @click="setOpen(false)">News</p>
          <p to="/contact" class="hover:text-orange-400 text-white transition-all duration-300" @click="setOpen(false)">Contact Us</p>
      </div>
    </div>
  </template>
  
  <script setup>  
  const props = defineProps({
    open: Boolean,
  });
  
  const emit = defineEmits(['set-open']);
  
  const setOpen = (val) => {
    emit('set-open', val);
  };
  </script>
  
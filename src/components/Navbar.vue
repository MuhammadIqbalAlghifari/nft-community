<template>
    <header ref="navbarRef" class="fixed z-50 w-full">
      <nav class="flex max-w-7xl mx-auto md:py-7 p-5 justify-between items-center w-full text-white">
        <MobileNav :open="open" @set-open="setOpen" />
        <div class="justify-between w-1/3 flex items-center">
            <p class="transition-all duration-300 text-sm text-white">Drop</p>
            <p class="transition-all duration-300 text-sm text-white">Marketplace</p>
            <p class="transition-all duration-300 text-sm text-white">Creator</p>
            <p class="transition-all duration-300 text-sm text-white">Community</p>
        </div>
        <ul class="md:flex hidden items-center justify-between xl:text-sm text-xs">
          <p class="transition-all duration-300 tracking-tighter text-sm text-white rounded-full bg-blue-600 px-4 py-3">Connect to wallet</p>
        </ul>
        <div class="flex relative w-8 h-8 flex-col justify-between items-center md:hidden" @click="toggleOpen">
          <span :class="['h-1 w-full rounded-lg transform transition duration-300 ease-in-out', open ? 'rotate-45 translate-y-3.5 bg-white' : 'bg-white']"></span>
          <span :class="['h-1 w-full rounded-lg transform transition-all duration-300 ease-in-out', open ? 'w-0 h-0' : 'bg-white w-full']"></span>
          <span :class="['h-1 w-full rounded-lg transform transition duration-300 ease-in-out', open ? '-rotate-45 -translate-y-3.5 bg-white' : 'bg-white']"></span>
        </div>
      </nav>
    </header>
  </template>
  
  <script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  import gsap from 'gsap';
  import MobileNav from './MobileNav.vue'; 
  
  const open = ref(false);
  const isScrolled = ref(false);
  const navbarRef = ref(null);
  
  const setOpen = (val) => {
    open.value = val;
  };
  
  const toggleOpen = () => {
    open.value = !open.value;
  };
  
  onMounted(() => {
    gsap.fromTo(navbarRef.value, { opacity: 0, y: -100 }, { opacity: 1, y: 0, duration: 1.5 });
  });
  
  onBeforeUnmount(() => {
  });
  </script>

  <style>
    .router-link-active {
      color: orange;
    }
  </style>
  
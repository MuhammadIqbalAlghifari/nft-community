<template>
    <Navbar/>
    <Hero/>
</template>

<script setup>

import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Lenis from 'lenis'
import { onMounted } from 'vue';

onMounted(() => {
    const lenis = new Lenis()

    function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
    }

    requestAnimationFrame(raf)
})

</script>
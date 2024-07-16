<template>
    <section class="flex flex-col lg:flex-row justify-start gap-y-10 lg:gap-y-0 items-center w-full lg:h-full">
        <div class="flex-col flex justify-center h-full lg:pt-40 pt-24 md:pt-28 max-w-7xl w-full mx-auto items-start">
            <div ref="heroLeft" class="flex-col px-10 md:16 lg:px-24 xl:px-0 flex justify-center max-w-4xl lg:gap-y-10 gap-y-5 lg:items-start items-center">
                <p class="text-white text-4xl lg:text-7xl text-center lg:text-start xl:text-[110px] leading-none" style="font-family: 'Monument Extended Ultrabold';">Create Your Own NFT Dream Gallery</p>
                <div class="flex flex-col-reverse lg:flex-row justify-center lg:gap-x-10 gap-y-5 items-center">
                    <div class="flex flex-col bg-blue-700 w-full lg:w-auto lg:px-3 lg:py-7 px-1 py-5 justify-center rounded-full items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="lg:size-10 size-5 text-white">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                        </svg>
                        <p class="text-white text-xs font-light">Discover NFT</p>
                    </div>
                    <p class="text-gray-400 lg:text-sm lg:text-start text-center text-xs max-w-lg">The largest nft maretplace. Authentic and truly unique digital creation. Signed and issued by the creator, made possible by blockchain technology</p>
                </div>
                <div class="flex lg:justify-start justify-center items-center lg:gap-x-10 gap-x-5">
                    <div class="flex-col text-white flex justify-center gap-y-2 lg:items-start items-center" v-for="(item, index) in DataHero" :key="index">
                        <p class="text-gray-400 lg:text-base text-center lg:text-start text-xs">{{ item.name }}</p>
                        <p class="text-white lg:text-2xl text-base text-center lg:text-start" style="font-family: 'Monument Extended Regular';">{{ item.points }}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="lg:absolute pb-20 lg:pb-0 relative flex w-full h-full lg:justify-end justify-center lg:items-center items-end -z-10">
            <div ref="heroRight" class="flex lg:w-3/5 w-full justify-center items-center z-10">
                <img src="/statue.png" alt="" class="lg:absolute px-6 sm:px-0 relative z-10 w-auto h-[500px] object-top object-cover">
                <img src="/bg-1.png" alt="" class="absolute lg:ml-12 px-4 sm:px-0 z-0 w-auto h-[430px] object-top object-cover">
                <img src="/bg-2.png" alt="" class="absolute lg:ml-64 px-2 sm:px-0 -z-10 w-auto h-[330px] object-top object-cover">
            </div>
            <img src="/line.png" alt="" class="absolute lg:flex -z-10 w-auto h-auto hidden">
        </div>
    </section>
    <div class="relative lg:flex w-full hidden h-full justify-between items-start z-10">
        <img ref="bottomLeft" src="/bottom-left.png" alt="" class="relative -ml-20 w-1/3 h-48 object-top object-cover">
        <img ref="bottomRight"src="/bottom-right.png" alt="" class="relative -mt-32 w-1/2 h-80 object-top object-cover">
    </div>
</template>

<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import { onMounted, ref } from 'vue';

const heroLeft = ref(null)
const heroRight = ref(null)
const bottomLeft = ref(null)
const bottomRight = ref(null)

gsap.registerPlugin(ScrollTrigger)

const animateOnDekstop = () => {
    gsap.fromTo(heroLeft.value.children, {opacity: 0 }, {opacity: 1, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: heroLeft.value.children,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(heroRight.value.children, {opacity: 0, x: 50 }, {opacity: 1, x:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: heroRight.value.children,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(bottomLeft.value, {opacity: 0, x: -100 }, {opacity: 1, x:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: bottomLeft.value,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(bottomRight.value, {opacity: 0, x: 100 }, {opacity: 1, x:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: bottomRight.value,
        start: "top bottom",
        end: "center center"
    }})
}

const animateOnMobile = () => {
    gsap.fromTo(heroLeft.value.children, {opacity: 0 }, {opacity: 1, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: heroLeft.value.children,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(heroRight.value.children, {opacity: 0, y: 50 }, {opacity: 1, y:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: heroRight.value.children,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(bottomLeft.value, {opacity: 0, x: -100 }, {opacity: 1, x:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: bottomLeft.value,
        start: "top bottom",
        end: "center center"
    }})
    gsap.fromTo(bottomRight.value, {opacity: 0, x: 100 }, {opacity: 1, x:0, duration: 1.5, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: bottomRight.value,
        start: "top bottom",
        end: "center center"
    }})
}

const DataHero = [
    {
        name: "Artwork",
        points: "25.5 K"
    },
    {
        name: "Artist",
        points: "15.5+ M"
    },
    {
        name: "Auciton",
        points: "10.5+ K"
    },
];

const isDekstop = window.matchMedia("(min-width: 1024px)").matches

onMounted(() => {
    isDekstop ? animateOnDekstop() : animateOnMobile()
})

</script>
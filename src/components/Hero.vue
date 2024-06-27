<template >
    <section class="flex justify-start items-center w-full h-full">
        <div class="flex-col flex justify-center h-full pt-40 max-w-7xl w-full mx-auto items-start">
            <div class="flex-col flex justify-center max-w-4xl gap-y-10 items-start">
                <p class="text-white text-[110px] leading-none" style="font-family: 'Monument Extended Ultrabold';">Create Your Own NFT Dream Gallery</p>
                <div class="flex justify-center gap-x-10 items-center">
                    <div class="flex flex-col bg-blue-700 px-3 py-7 justify-center rounded-full items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-10 text-white">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                        </svg>
                        <p class="text-white text-xs font-light">Discover NFT</p>
                    </div>
                    <p class="text-gray-400 text-sm max-w-lg">The largest nft maretplace. Authentic and truly unique digital creation. Signed and issued by the creator, made possible by blockchain technology</p>
                </div>
                <div class="flex justify-start items-center gap-x-10">
                    <div class="flex-col text-white flex justify-center gap-y-2 items-start" v-for="(item, index) in DataHero" :key="index">
                        <p class="text-gray-400 text-base">{{ item.name }}</p>
                        <p class="text-white text-2xl" style="font-family: 'Monument Extended Regular';">{{ item.points }}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="absolute flex w-full h-full justify-end items-center -z-10">
            <div class="flex w-3/5 justify-center items-center z-10">
                <img src="/statue.png" alt="" class="absolute z-10 w-auto h-[500px] object-top object-cover">
                <img src="/bg-1.png" alt="" class="absolute ml-12 z-0 w-auto h-[430px] object-top object-cover">
                <img src="/bg-2.png" alt="" class="absolute ml-64 -z-10 w-auto h-[330px] object-top object-cover">
            </div>
            <img src="/line.png" alt="" class="absolute -z-10 w-auto h-auto">
        </div>
    </section>
    <div class="relative flex w-full h-full justify-between items-start z-50">
        <img src="/bottom-left.png" alt="" class="relative -ml-20 w-1/3 h-48 object-top object-cover">
        <img src="/bottom-right.png" alt="" class="relative -mt-32 w-1/2 h-80 object-top object-cover">
    </div>
</template>

<script setup>

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
]

</script>
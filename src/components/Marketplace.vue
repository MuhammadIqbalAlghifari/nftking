<template>
    <div class="absolute -z-10 flex justify-end items-start w-full h-full">
        <div class="rounded-full w-1/2 h-5/6 -ml-12 md:-ml-32 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <main class="xl:max-w-7xl xl:mx-auto md:p-14 lg:px-16 md:py-24 py-20 xl:px-0 flex flex-col justify-center lg:gap-y-20 gap-y-10 items-center h-full px-5 md:pt-20 pt-16">
        <div class="flex justify-between w-full flex-col items-center gap-y-5 lg:gap-y-10">
            <h1 class="xl:text-6xl md:text-4xl text-2xl lg:text-start text-center leading-snug lg:leading-snug font-bold text-white" style="font-family: 'Poppins';">Explore Marketplace</h1>
            <div class="flex xl:justify-between justify-center gap-2 lg:gap-2 items-center max-w-7xl mx-auto flex-wrap w-full">
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent px-6 py-2">Collectibles</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-2">Art</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Gaming</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Sports</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Photography</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Music</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Virtual Worlds</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent hidden md:flex px-6 py-2">Trading Cards</button>
                <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent flex md:hidden px-6 py-2">+6</button>
            </div>
        </div>
        <main class="grid lg:grid-cols-4 md:grid-cols-2 grid-cols-1 w-auto h-auto place-items-center justify-between gap-5 flex-wrap">
            <div class="flex-col group hover:border-white px-4 py-4 md:gap-y-10 gap-y-5 hover:border-[1.5px] rounded-2xl bg-slate-300 bg-opacity-10 backdrop-blur-md transition-all duration-200 justify-center w-auto h-auto flex items-center" v-for="(item, index) in TrendingData" :key="index">
                <img :src="item.image" class="w-auto rounded-xl z-0 h-auto object-cover object-center"/>
                <div class="flex justify-between items-center w-full">
                    <div class="flex-col justify-center items-start flex gap-y-1.5">
                        <div style="font-family: 'Roboto';" class="flex-col justify-center items-start flex gap-y-2">
                            <h1 class="text-white xl:text-xl md:text-lg text-base font-semibold">{{ item.author }}</h1>
                            <p class="text-slate-400 xl:text-sm text-xs">{{ item.username }}</p>
                        </div>
                    </div>
                    <h2 style="font-family: 'Roboto';" class="bg-clip-text bg-gradient-to-br from-[#FF8D8D] to-[#F7FC0E] text-transparent font-extrabold xl:text-xl md:text-lg text-base">{{ item.worth }}</h2>
                </div>
            </div>
        </main>
        <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full border-[#3633D0] border-[2px] bg-transparent px-6 py-2">View More</button>
    </main>
    <div class="absolute -z-10 flex justify-start items-start w-full h-full">
        <div class="rounded-full w-1/3 h-3/6 -mt-96 -ml-12 md:-ml-32 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <div class="absolute -z-10 flex justify-center items-start w-full h-full">
        <div class="rounded-full w-1/3 h-3/6 -ml-12 md:-ml-32 bg-gradient-to-b blur-[120px] from-[#F3BA2F] to-[#06132D]"></div>
    </div>
</template>

<script setup>
const TrendingData = [
    {
        image: '/Inception.png',
        author: "Inception",
        username: "@Ioifonsaf",
        worth: "0.8 ETH",
    },
    {
        image: '/sink love.png',
        author: "Sink Love",
        username: "@hibnastiar",
        worth: "1.4 ETH",
    },
    {
        image: '/Moonshine.png',
        author: "Moonshine",
        username: "@rere2880",
        worth: "0.5 ETH",
    },
    {
        image: '/Petition.png',
        author: "Petition",
        username: "@downhill",
        worth: "1.3 ETH",
    },
    {
        image: '/Metomorph.png',
        author: "Metamorph",
        username: "@reaflu",
        worth: "1.0 ETH",
    },
    {
        image: '/Castel.png',
        author: "Castel Sand",
        username: "@zinksu",
        worth: "0.7 ETH",
    },
    {
        image: '/Nuckle.png',
        author: "Nuckle",
        username: "@zoldick",
        worth: "1.3 ETH",
    },
    {
        image: '/incublast.png',
        author: "Incublast",
        username: "@mikeyobstain",
        worth: "1.1 ETH",
    },
]
</script>
<template>
    <div class="absolute -z-10 flex justify-start items-start w-full h-full">
        <div class="rounded-full w-1/3 h-5/6 md:-mt-20 -mt-10 -mr-12 md:-mr-32 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <div class="absolute -z-10 flex  mt-80 justify-center items-center w-full h-full">
        <div class="rounded-full w-1/2 h-5/6 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <main class="xl:max-w-7xl xl:mx-auto md:p-14 lg:px-16 md:py-24 py-20 xl:px-0 flex flex-col justify-center lg:gap-y-20 gap-y-10 items-center h-full px-5 md:pt-20 pt-16">
        <div class="flex justify-between w-full flex-col lg:flex-row lg:items-start items-center gap-y-5 lg:gap-y-0">
            <h1 class="xl:text-6xl md:text-4xl text-2xl lg:text-start text-center leading-snug lg:leading-snug font-bold text-white" style="font-family: 'Poppins';">Trending This Week</h1>
            <p class="xl:text-xl md:text-base text-sm text-slate-400 lg:text-justify text-center max-w-lg" style="font-family: 'Gt Walsheim Pro Light';">Various kinds of Artwork categories that are trending this week. The trend will be reset every week. Don’t miss out on the best artworks every week</p>
        </div>
        <main class="flex xl:justify-between justify-center items-center w-full h-auto gap-10 flex-wrap mx-auto max-w-5xl">
            <div class="flex-col justify-center w-auto h-auto flex items-center" v-for="(item, index) in TrendingData" :key="index">
                <img :src="item.image" class="w-11/12 rounded-xl border-[1.5px] border-white relative z-0 h-auto object-cover object-center"/>
                <div class="flex items-center border-white md:px-6 md:py-4 px-4 py-2 border-[1.5px] md:-mt-20 -mt-10 rounded-lg bg-slate-300 bg-opacity-10 backdrop-blur-md justify-between w-full">
                    <div class="flex-col justify-center items-start flex gap-y-1.5">
                        <div style="font-family: 'Roboto';" class="flex-col justify-center items-start flex gap-y-0.5">
                            <h1 class="text-white xl:text-xl md:text-lg text-base font-semibold">{{ item.author }}</h1>
                            <p class="text-slate-400 xl:text-sm text-xs">{{ item.username }}</p>
                        </div>
                        <h2 style="font-family: 'Roboto';" class="bg-clip-text bg-gradient-to-br from-[#FF8D8D] to-[#F7FC0E] text-transparent font-extrabold xl:text-xl md:text-base text-sm">{{ item.worth }}</h2>
                    </div>
                    <button class="transition-all duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] md:px-6 md:py-2 px-3 py-1.5">Collect Now</button>
                </div>
            </div>
        </main>
    </main>
</template>

<script setup>
const TrendingData = [
    {
        image: '/hand.png',
        author: "Miles Grogosters",
        username: "@rominolegs",
        worth: "4.99 ETH",
    },
    {
        image: '/paint.png',
        author: "Reox Fancxy",
        username: "@hibnastiar",
        worth: "3.27 ETH",
    },
    {
        image: '/ymir.png',
        author: "Miles Grogosters",
        username: "@senjadisini",
        worth: "4.20 ETH",
    },
    {
        image: '/monalisa.png',
        author: "Tuinz Rey",
        username: "@albertov",
        worth: "2.99 ETH",
    },
]
</script>
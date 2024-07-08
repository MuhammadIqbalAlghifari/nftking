<template>
    <div class="absolute -z-10 flex justify-end items-start overflow-hidden w-full h-full">
        <div class="rounded-full w-1/3 h-4/5 md:-mt-20 -mt-10 -mr-12 md:-mr-32 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <main class="xl:max-w-7xl xl:mx-auto md:px-14 lg:px-16 xl:px-0 flex flex-col lg:flex-row justify-center gap-y-10 lg:gap-y-0 lg:justify-between items-center h-full lg:pt-0 px-5 md:pt-20 xl:pt-0 pt-16 lg:h-screen">
        <div class="flex-col flex justify-center lg:items-start items-center gap-y-5">
            <h1 class="xl:text-6xl md:text-4xl text-2xl lg:text-start text-center leading-snug max-w-2xl lg:leading-snug font-bold text-white" style="font-family: 'Inter Variable';">Discover & Collect <span class="text-transparent bg-clip-text bg-gradient-to-r from-[#FF8D8D] to-[#F7FC0E]">Super Rare</span> Digital Artworks</h1>
            <p class="xl:text-base md:text-sm text-xs text-white lg:text-start text-center max-w-lg" style="font-family: 'Inter Variable';">The largest NFT marketplace. Authentic and truly unique digital creation. Signed and issued by the creator, made possible by blockchain technology</p>
            <div class="flex justify-center items-center gap-x-5"  style="font-family: 'Roboto';">
                <p class="transition-all duration-300 tracking-wide xl:text-sm text-xs text-white rounded-full font-medium bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-3" style="font-family: 'Roboto';">Let's Explore</p>
                <p class="transition-all duration-300 tracking-wide xl:text-sm text-xs text-white rounded-full font-medium bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-3" style="font-family: 'Roboto';">Sell NFT</p>
            </div>
        </div>
        <div class="relative z-10 w-full h-auto lg:h-screen max-w-2xl flex flex-col justify-end p-14 items-center">
            <div class="w-full z-0 h-full relative flex justify-center items-center">
                <img src="/egypt.png" alt="pic 1" class="relative rounded-lg z-0 border-white border-[1.5px] w-auto h-auto">
                <img src="/violet.png" alt="pic 1" class="absolute rotate-[8deg] lg:mt-7 lg:ml-20 border-white border-[1.5px] rounded-lg -z-10 w-auto h-auto">
                <img src="/flower.png" alt="pic 1" class="absolute rounded-lg lg:ml-40 lg:mt-6 rotate-[16deg] border-white border-[1.5px] -z-20 w-auto h-auto">
            </div>
            <div class="md:w-auto w-full z-10 md:p-10 p-5 h-auto absolute rounded-lg flex gap-x-5 border-white border-[1.5px] bg-slate-300 bg-opacity-10 backdrop-blur-md justify-center items-center">
                <img src="/metamask.png" alt="pic 1" class="w-auto h-auto">
                <img src="/binance.png" alt="pic 1" class="w-auto hidden md:flex h-auto">
                <img src="/coinbase.png" alt="pic 1" class="w-auto hidden md:flex h-auto">
            </div>
        </div>
    </main>
</template>

<script>
export default {
    
}
</script>
<template>
    <div class="absolute -z-10 flex justify-between mt-80 items-end w-full h-full">
        <div class="rounded-full w-1/3 h-1/3 lg:-ml-12 md:-ml-32 bg-gradient-to-t blur-[120px] from-[#725BDA] to-[#06132D]"></div>
        <div class="rounded-full w-1/3 h-1/3 bg-gradient-to-b blur-[120px] from-[#725BDA] to-[#06132D]"></div>
    </div>
    <main class="xl:max-w-7xl xl:mx-auto md:p-14 lg:px-16 md:py-24 xl:px-0 flex flex-col justify-center lg:gap-y-10 gap-y-5 items-center h-full px-5 md:pt-20 pt-16">
        <div class="flex justify-between w-full flex-col items-center gap-y-5 lg:gap-y-10">
            <h1 ref="tittleSection" class="xl:text-6xl md:text-4xl text-2xl lg:text-start text-center leading-snug lg:leading-snug font-bold text-white" style="font-family: 'Poppins';">Top List Creator</h1>
            <div ref="buttonSection" class="flex lg:justify-between justify-center gap-2 lg:gap-2 items-center max-w-xs mx-auto flex-wrap lg:w-[25%] xl:w-[20%] md:h-3/4 w-full">
                <button class="tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-2">Popular</button>
                <button class="tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-2">Following</button>
            </div>
        </div>
        <main class="grid lg:grid-cols-4 md:grid-cols-2 grid-cols-1 w-auto h-auto place-items-center justify-between gap-5 flex-wrap">
            <div ref="creatorCards" class="flex-col group hover:border-white overflow-hidden gap-y-10 hover:border-[1.5px] rounded-2xl bg-slate-300 bg-opacity-10 backdrop-blur-md  duration-200 justify-center w-auto h-auto flex items-center" v-for="(item, index) in CreatorData" :key="index">
                <img :src="item.image" class="w-auto rounded-b-3xl z-0 h-auto object-cover object-center"/>
                <div class="flex flex-col justify-center gap-y-5 -mt-20 z-10 p-3 items-center w-full">
                    <div class="flex-col justify-center items-start flex gap-y-1.5">
                        <div style="font-family: 'Roboto';" class="flex-col justify-center items-center flex gap-y-3">
                            <div style="font-family: 'Roboto';" class="flex-col justify-center items-center flex gap-y-1">
                                <img :src="item.author" alt="profile pic" class="w-14 rounded-full h-14 object-center object-cover">
                                <h1 class="text-white xl:text-xl md:text-lg text-base font-normal">{{ item.username }}</h1>
                            </div>
                            <h2 style="font-family: 'Roboto';" class="bg-clip-text bg-gradient-to-br from-[#FF8D8D] to-[#F7FC0E] text-transparent font-extrabold xl:text-xl md:text-lg text-base">{{ item.worth }} <span class="bg-clip-text bg-gradient-to-br from-[#FF8D8D] to-[#F7FC0E] text-transparent text-sm font-light">Artwork</span></h2>
                        </div>
                    </div>
                    <button class="tracking-wide xl:text-base w-full md:text-sm text-xs text-white rounded-xl border-[#3633D0] border-[2px] bg-transparent px-6 py-2">Followed</button>
                </div>
            </div>
        </main>
    </main>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';

gsap.registerPlugin(ScrollTrigger)

const tittleSection = ref(null)
const buttonSection = ref(null)
const creatorCards = ref([])
const buttonView = ref(null)

const animateOnDekstop = () => {
    gsap.fromTo(tittleSection.value, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: tittleSection.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }}) 
    gsap.fromTo(buttonSection.value.children, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: buttonSection.value.children,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
    creatorCards.value.forEach(child => {
        gsap.fromTo(child, {opacity: 0, y: 50}, {opacity: 1, y:0, duration: 1, delay: 0.2, ease: 'power3.out', scrollTrigger: {
            trigger: child,
            start: 'top bottom',
            end: 'bottom top',
            scrub: false,
            toggleActions: 'play reverse play reverse'
        }}) 
    })
    gsap.fromTo(buttonView.value, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: buttonView.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
}

const animateOnMobile = () => {
    gsap.fromTo(tittleSection.value, {opacity: 0, y: 10}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: tittleSection.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }}) 
    gsap.fromTo(buttonSection.value, {opacity: 0, y: 10}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: buttonSection.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
    creatorCards.value.forEach(child => {
        gsap.fromTo(child, {opacity: 0, y: 10}, {opacity: 1, y:0, duration: 1, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: child,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
        }}) 
    }) 
    gsap.fromTo(buttonView.value, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: buttonView.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
}

const isDekstop = window.matchMedia("(min-width: 1024px)").matches

onMounted(() => {
    isDekstop ? animateOnDekstop() : animateOnMobile()
})

const CreatorData = [
    {
        image: '/hibnastiar.png',
        author: "/hibnastiar pfp.png",
        username: "Hibnastiar",
        worth: "27.3K",
    },
    {
        image: '/tukrim.png',
        author: "/tukrim pfp.png",
        username: "Tukirin",
        worth: "21.6K",
    },
    {
        image: '/aksaraz.png',
        author: "/aksaraz pfp.png",
        username: "Aksaraz",
        worth: "14.0K",
    },
    {
        image: '/yuk john.png',
        author: "/yuk john pfp.png",
        username: "Yuk Jum",
        worth: "11.9K",
    },
]
</script>
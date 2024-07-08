<template>
    <section class="xl:max-w-7xl xl:mx-auto md:p-14 lg:px-16 xl:px-0 pt-16 pb-10 px-5 flex flex-col justify-center items-center gap-y-10">
        <main ref="bgFooter"class="rounded-2xl bg-slate-300 bg-opacity-10 backdrop-blur-md flex flex-col justify-center w-full lg:gap-y-10 py-10 px-5 md:px-10 xl:px-0 md:py-20 gap-y-5 items-center h-full">
            <div ref="footerSentence" class="flex justify-between max-w-3xl w-full flex-col items-center lg:gap-y-12 gap-y-6">
                <div class="flex justify-between w-full flex-col items-center gap-y-5">
                    <h1 class="xl:text-4xl md:text-2xl text-xl lg:text-start text-center leading-snug lg:leading-snug font-bold text-white" style="font-family: 'Poppins';">Never miss a drop!</h1>
                    <p class="text-white xl:text-base text-center md:text-sm text-xs">Subscribe to super-exclusive drop list and be the first to know about upcoming drops</p>
                </div>
                <div class="flex flex-col gap-y-5 md:gap-y-0 md:flex-row justify-between lg:gap-x-10 gap-x-5 w-full items-center">
                    <input type="text" placeholder="Enter your email address" class="w-full md:text-start text-center xl:text-base md:text-sm text-xs outline-none placeholder:text-slate-300 text-white bg-slate-300 bg-opacity-10 backdrop-blur-md rounded-full px-6 py-3">
                    <button class="transition-all w-full md:w-auto duration-300 tracking-wide xl:text-base md:text-sm text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-6 py-3">Subscribe</button>
                </div>
            </div>
        </main>
        <p ref="currentYear" class="text-white xl:text-sm text-xs text-center">2018 - {{ year }} NFTKING, Inc</p>
    </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';

gsap.registerPlugin(ScrollTrigger)

const bgFooter = ref(null)
const footerSentence = ref(null)
const currentYear = ref(null)

const animateOnDekstop = () => {
    gsap.fromTo(bgFooter.value, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: bgFooter.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }}) 
    gsap.fromTo(footerSentence.value.children, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: footerSentence.value.children,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
    gsap.fromTo(currentYear.value, {opacity: 0, y: 50}, {opacity: 1, y:0, duration: 1, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: currentYear.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }}) 
}

const animateOnMobile = () => {
    gsap.fromTo(bgFooter.value, {opacity: 0, y: 10}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: bgFooter.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }}) 
    gsap.fromTo(footerSentence.value, {opacity: 0, y: 10}, {opacity: 1, y: 0, duration: 1, delay: 0.3, ease: 'power3.out', scrollTrigger: {
        trigger: footerSentence.value,
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
    }})   
    gsap.fromTo(currentYear.value, {opacity: 0, y: 10}, {opacity: 1, y:0, duration: 1, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: currentYear.value,
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

const year = new Date().getFullYear()
</script>
<template>
    <header ref="navbarRef" :class="['fixed z-50 w-full transition-colors duration-500 border-b-white border-opacity-[0.2] border-b', isScrolled ? 'bg-slate-300 bg-opacity-10 backdrop-blur-md border-none' : 'bg-transparent']">
      <nav class="flex px-7 md:px-14 lg:px-16 py-3 xl:px-0 xl:max-w-7xl xl:mx-auto justify-between items-center w-full text-white">
        <MobileNav :open="open" @set-open="setOpen" />
        <div class="justify-between xl:w-[20%] xl:gap-x-0 md:gap-x-4 hidden md:flex items-center">
            <p class="transition-all duration-300 text-sm text-white" style="font-family: 'GT Walsheim Pro Regular';">Marketplace</p>
            <p class="transition-all duration-300 text-sm text-white" style="font-family: 'GT Walsheim Pro Regular';">Creator</p>
            <p class="transition-all duration-300 text-sm text-white" style="font-family: 'GT Walsheim Pro Regular';">Community</p>
        </div>
        <p class="transition-all flex duration-300 text-lg text-white" style="font-family: 'GT Walsheim Pro Bold';">NFTKING</p>
        <ul class="md:flex hidden items-center justify-between xl:text-sm text-xs">
          <button class="transition-all duration-300 tracking-wide xl:text-base text-xs text-white rounded-full bg-gradient-to-br from-[#89C6FF] to-[#3633D0] px-4 py-3" style="font-family: 'Roboto';">Connect wallet</button>
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

  const handleScroll = () => {
    isScrolled.value = window.scrollY > 50
  }

  const setOpen = (val) => {
    open.value = val;
  };
  
  const toggleOpen = () => {
    open.value = !open.value;
  };
  
  onMounted(() => {
    gsap.fromTo(navbarRef.value, { opacity: 0, y: -100 }, { opacity: 1, y: 0, duration: 1.5 });
    window.addEventListener('scroll', handleScroll);
      return () => {
        window.removeEventListener('scroll', handleScroll);
      };
  });
  
  onBeforeUnmount(() => {
  });
  </script>

  <style>
    .router-link-active {
      color: orange;
    }
  </style>
  
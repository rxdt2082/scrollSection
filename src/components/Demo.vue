<template>
    <div class="process">
      <div class="process__container">
        <!-- <div class="process__item" v-for="item in items" :key="item">
          {{item}}
        </div> -->
        <div class="pr-12 sm:pr-24 md:pr-[10rem] xl:pr-[20rem] flex-shrink-0 process__item">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="pr-12 sm:pr-24 md:pr-[10rem] xl:pr-[20rem] flex-shrink-0 process__item">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="pr-12 sm:pr-24 md:pr-[10rem] xl:pr-[20rem] flex-shrink-0 process__item">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="pr-12 sm:pr-24 md:pr-[10rem] xl:pr-[20rem] flex-shrink-0 process__item">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="pr-12 sm:pr-24 md:pr-[10rem] xl:pr-[20rem] flex-shrink-0 process__item">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
      </div>
    </div>
  </template>
  
  <script>
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  
  gsap.registerPlugin(ScrollTrigger);
  export default {
    data() {
      return {
        items: Array.from({ length: 5 }, (_, i) => i + 1), // Adjust the number of sections
      };
    },
    mounted() {
      setTimeout(() => {
        this.initScrollAnimation();
      }, 2000);
    },
    methods: {
      initScrollAnimation() {
        const process = document.querySelector('.process__container');
        // const processItem = document.querySelector('.process__item');
        let processWidth = process.offsetWidth;
        // let processItemWidth = processItem.offsetWidth;
    //    setTimeout(() => {
    //     process.style.width = processItemWidth * 7;
    //     console.log(process.style.width = processItemWidth * 7)
    //    }, 2000);
        let amountToScroll = processWidth - window.innerWidth;
        
        const ScrollSection = gsap.to(process, {
            x: -amountToScroll,
            ease: "none"
        })

        ScrollTrigger.create({
            trigger:".process",
            start: "top top",
            end:"+=" + amountToScroll,
            pin: true,
            animation: ScrollSection,
            scrub: 1,
            markers: true
        })
      },
    },
  };
  </script>
  
  <style scoped>
  .process {
    width: 100%;
    overflow: hidden;
    position: relative;
    height: 100vh;
    padding: 100px 0;
  }
  
  .process__container {
    display: flex;
    width: calc(820px * 5); /* Adjust the width based on the number of sections */
  }
  
  .process__item {
    /* flex: 1; */
    width: 821px;
    background-color: #2b518bd2;
  }
  </style>
  
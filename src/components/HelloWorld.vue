<template>
  
  <!-- <section class=" bg-pastel-2 TeamSlider  z-10 overflow-hidden"> -->
            <!-- <h2 class="text-[5rem] md:text-[9.375rem] xl:text-[15rem] w-full leading-tight text-center absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 px-4">{{ data.title }}</h2> -->
            <div class="horizontal-container">
                <div class="horizontal-wrapper">
                    <div class="horizontal-scroller">
                        <div class="row py-[3.75rem] md:py-20 xl:py-32">
                            <div class="mr-12 sm:mr-24 md:mr-[10rem] xl:mr-[20rem] flex-shrink-0">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="mr-12 sm:mr-24 md:mr-[10rem] xl:mr-[20rem] flex-shrink-0">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="mr-12 sm:mr-24 md:mr-[10rem] xl:mr-[20rem] flex-shrink-0">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                            <div class="mr-12 sm:mr-24 md:mr-[10rem] xl:mr-[20rem] flex-shrink-0">
                                <img class="w-[12.5rem] md:w-[21.875rem] xl:w-[500px]" src="https://s3.ap-south-1.amazonaws.com/images.onprintshop/Naresh_Devra_ccd363ac45.png" >
                            </div>
                        </div>
                    </div>
                </div>
            </div>
    <!-- </section> -->
</template>
<script type="text/javascript">

import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
    props:{
        data:Object
    },
    mounted() {
        
            const containerMain = document.querySelector(".horizontal-container");
            const container = document.querySelector(".horizontal-scroller");
            const containerWidth = container.scrollWidth - window.innerWidth;
            // Create the GSAP animation
            gsap.to(container, {
            x: () => -containerWidth,
            scrollTrigger: {
                markers: false,
                trigger: '.horizontal-wrapper',
                start: 'top top',
                scrub: 0.5,
                pin: '.horizontal-container',
                end: () => "+=" + containerWidth,
                invalidateOnRefresh: true,
                // onEnter: () => {
                // // When the animation starts, set position to fixed
                // setTimeout(() => {
                //     containerMain.style.position = 'fixed'; 
                //     containerMain.style.transform = 'translate(0px, 0px)'; 
                // }, 20);
                // },
                // onLeaveBack: () => {
                // // When scrolling back, set position to absolute (or any appropriate position)
                // containerMain.style.position = '';
                // },
            }
            });  
    },
}   

</script>
<style scoped>
.horizontal-scroller {
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  gap: 5px;
  width: 100%;
  height: 100vh;
}
.horizontal-wrapper {
  width: 100%;
  height: calc(100vh + 210vw);
}

.horizontal-container {
  width: 100%;
  height: calc(100vh + 210vw);
  margin-top: 2em;
}

.horizontal-scroller .row {
  display: flex;
  justify-content: flex-start;
  gap: 5px;
}
</style>
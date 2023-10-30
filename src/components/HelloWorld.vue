<template>
    <div class="firstContainer">
        <h1>Testing horizontal scrolling w/ three sections</h1>
        <h2>First Container</h2>
        </div>
        <div class="container">
        <div class="description panel blue">
            <div>
            SCROLL DOWN
            <div class="scroll-down"><div class="arrow"></div></div>
            </div>
        </div>

        <section class="panel red">
            ONE
        </section>
        <section class="panel orange">
            TWO
        </section>
        <section class="panel purple">
            THREE
        </section>
        </div>
        <div class="lastContainer">
        Last Container
        </div>
</template>
<script type="text/javascript">
console.clear();
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";


// if (process.client)
setTimeout(() => {
    gsap.registerPlugin(ScrollTrigger);

let sections = gsap.utils.toArray(".panel");

gsap.to(sections, {
  xPercent: -100 * (sections.length - 1),
  ease: "none",
  scrollTrigger: {
    trigger: ".container",
    pin: true,
    scrub: 1,
    // snap: 1 / (sections.length - 1),
    end: () => "+=" + document.querySelector(".container").offsetWidth
  }
});
}, 2000);



// const slides = [
//   { id: "one", color: "teal" },
//   { id: "two", color: "orange" },
//   { id: "three", color: "emerald" },
//   { id: "four", color: "indigo" },
//   { id: "five", color: "pink" },
//   { id: "six", color: "teal" }
// ];
</script>





<!-- I've used tailwind in my actual app but can't seem to get that to work here so included the exact same styles below too -->
<style>
html {
	overflow-y: scroll;
	height: 100%;
	-webkit-overflow-scrolling: touch;
	overflow-scrolling: touch;
}
body {
	overflow-y: visible;
	position: relative;
  height: unset;
}
html, body {
	overflow-x: hidden;
	margin: 0;
}

.container {
	width: 400%;
	height: 100vh;
	display: flex;
	flex-wrap: nowrap;
}

.firstContainer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: yellow;
}
.panel {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: 600;
    font-size: 1.5em;
    text-align: center;
    color: white;
    position: relative;
    box-sizing: border-box;
    padding: 10px;
}
.red{
    background: red;
}
.orange{
    background: orange;
}
.purple{
    background: purple;
}
.blue{
    background: blue;
}
.lastContainer {
  display: flex;
  height: 100vh;
  background: yellow;
}</style>

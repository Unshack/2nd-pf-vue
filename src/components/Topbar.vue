<template>
  <header>
    <div class="header container">
      <div>
        <p class="circle" id="copyright">©</p>
        <p class="circle">F</p>
        <p class="circle">R</p>
        <p class="circle">I</p>
        <p class="circle">E</p>
        <p class="circle">N</p>
        <p class="circle">C</p>
        <p class="circle">E</p>
      </div>

      <div class="controls">
        <div class="nav-links">
          <a href="#" @click="lenis.scrollTo('#work')" class="nav-link">
            WORK</a
          >
          <a href="#" @click="lenis.scrollTo('#skills')" class="nav-link">
            SKILLS</a
          >
          <a href="#" @click="lenis.scrollTo('#contact')" class="nav-link">
            CONTACT</a
          >
        </div>

        <div class="header-buttons">
          <a target="_blank" href="/marckoDev.pdf">
            <button type="button" class="btn btn_download">
              <span>DOWNLOAD RESUME</span>
            </button>
          </a>
        </div>

        <div @click="toggleLight()" class="switch">
          <Switch />
        </div>

        <div @click="toggleNav()" class="hamburger">
          <Hamburger :active="mobileNavActive" />
        </div>
      </div>
    </div>
  </header>
  <MobileNav @toggleActive="toggleNav()" :active="mobileNavActive" />
</template>

<script setup>
import Switch from "./icons/Switch.vue";
import Hamburger from "./icons/Hamburger.vue";
import MobileNav from "./MobileNav.vue";
import { onMounted, ref } from "vue";
import { lenis } from "../helpers/animations";
import gsap from "gsap";

onMounted(() => {
  gsap.from(".circle", {
    y: "random(-400, 200)",
    opacity: 0,
    duration: 1,
    stagger: 0.2,
    delay: 2,
  });
});

const mobileNavActive = ref(false);

function toggleLight() {
  document.querySelector("body").classList.toggle("light");
}

function toggleNav() {
  mobileNavActive.value = !mobileNavActive.value;
  document.querySelector("header").classList.toggle("fixed");
}
onMounted(() => {});
</script>

<style lang="scss" scoped>
@import "@/assets/variables.scss";

header.fixed {
  position: fixed;
  z-index: 10;
  width: 100%;
  background: $black;
  transition: all 0.5s ease;
}

a > .circle {
  font-weight: bold;
}
#copyright {
  margin-right: 5px;
}
.switch {
  @media (max-width: $small) {
    display: none;
  }
}
</style>

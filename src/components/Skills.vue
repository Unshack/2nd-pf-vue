<template>
  <section class="skills-section" id="skills">
    <SectionHeader :text="'SKILLS'" />
    <div class="skills">
      <div class="skillset--1">
        <h2>
          <span>Javascript</span> . <span>Redux</span> .
          <span>Typescript</span> . <span>ReactJS</span> . <span>Redux</span> .
          <span>TanStack</span> . <span>TanStack</span> . <span>Query</span>
        </h2>
      </div>
      <div class="skillset--2">
        <h2>
          <span>NextJS</span> . <span>Express</span> . <span>Tailwind</span> .
          <span>Git</span> . <span>NextJS</span> . <span>MongoDb</span> .
          <span>Tailwind</span> . <span>Git</span> . <span>NextJS</span> .
          <span>NodeJS</span> . <span>Tailwind</span> . <span>Git</span>
        </h2>
      </div>
      <div class="skillset--1">
        <h2>
          <span>HTML</span> . <span>CSS</span> . <span>SCSS</span> .
          <span>Bootstrap</span> . <span>HTML</span> . <span>CSS</span> .
          <span>SCSS</span> . <span>Bootstrap</span>
        </h2>
      </div>
      <div class="skillset--2">
        <h2>
          <span>AdobeXD</span> . <span>Figma</span> . <span>Wordpress</span> .
          <span>AdobeXD</span> . <span>Figma</span> . <span>Wordpress</span> .
          <span>AdobeXD</span> . <span>Figma</span> . <span>Wordpress</span> .
        </h2>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from "vue";
import SectionHeader from "./SectionHeader.vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: ".skills-section .skills",
      start: "top bottom",
      end: "bottom+=200 top",
      scrub: true,
    },
  });

  tl.fromTo(".skillset--1 h2", { x: "20%" }, { x: "-20%" }, 0).fromTo(
    ".skillset--2 h2",
    { x: "-20%" },
    { x: "20%" },
    0
  );
});
</script>

<style lang="scss" scoped>
@import "@/assets/variables.scss";
</style>

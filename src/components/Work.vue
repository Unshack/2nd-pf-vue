<template>
  <section class="work-section" id="work">
    <SectionHeader :text="'WORK'" />
    <div class="">
      <div class="projects">
        <div
          @click="openTab('https://gallant-homes.onrender.com/')"
          class="project"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>Gallant Homes</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Express</span>
              <span style="--i: 3">MongoDb</span>
            </div>
          </div>
          <div class="image">
            <a
              name="Gallant Homes"
              target="_blank"
              href="https://gallant-homes.onrender.com/"
              ><img alt="Gallant Homes" src="/images/gallant.png" />
            </a>
          </div>
        </div>

        <div
          @click="openTab('https://trip-guide-sigma.vercel.app/')"
          class="project"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>Trip Guide</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Material UI</span>
            </div>
          </div>
          <div style="background-color: #111119" class="image">
            <a
              name="trip-guide"
              target="_blank"
              href="https://trip-guide-sigma.vercel.app/"
            >
              <img alt="Trip Guide" src="/images/trip.png" />
            </a>
            <div class="cursor"><p>View Site</p></div>
          </div>
        </div>

        <div
          @click="openTab('https://frontend-social-6dec.onrender.com/')"
          class="project"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>Social Media Lagoon</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux ToolKit</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Express</span>
              <span style="--i: 3">MongoDb</span>
              <!-- <span style="--i: 5">LENIS</span> -->
            </div>
          </div>
          <div style="background-color: #131313" class="image">
            <a
              name="Project Portfolio"
              target="_blank"
              href="https://frontend-social-6dec.onrender.com/"
              ><img alt="Project Portfolio" src="/images/lagoon.png"
            /></a>
          </div>
        </div>
        <div
          @click="openTab('https://shirt-final-6hhb.vercel.app/')"
          class="project"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>ShirtThreads</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Express</span>
              <span style="--i: 3">MongoDb</span>
              <span style="--i: 3">Stripe</span>
            </div>
          </div>
          <div class="image">
            <a
              name="ShirtThreads"
              target="_blank"
              href="https://shirt-final-6hhb.vercel.app/"
              ><img alt="ShirtThreads" src="/images/shirt.png" />
            </a>
          </div>
        </div>

        <div
          @click="openTab('https://adminfin.netlify.app/')"
          v-show="more"
          class="project more"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>FinHub</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Material UI</span>
            </div>
          </div>
          <div style="background-color: white" class="image">
            <a
              name="FinHub"
              target="_blank"
              href="https://adminfin.netlify.app/"
            >
              <img alt="FinHub" src="/images/admindashboard.png" />
            </a>
          </div>
        </div>
        <div
          @click="openTab('https://money-go.netlify.app/')"
          v-show="more"
          class="project more"
        >
          <div class="container">
            <div class="dot"></div>
            <h3>Money Changer UI</h3>
          </div>
          <div class="container">
            <div class="skills">
              <span style="--i: 0">React</span>
              <span style="--i: 1">Redux</span>
              <span style="--i: 2">Tailwind CSS</span>
              <span style="--i: 3">Material UI</span>
            </div>
          </div>
          <div class="image">
            <a
              name="Money Changer UI"
              target="_blank"
              href="https://money-go.netlify.app/"
              ><img alt="Money Changer UI" src="/images/money.png" />
            </a>
          </div>
        </div>

        <div @click="toggleLoadMore()" class="load-more">
          <p>SEE MORE</p>
          <div class="plus">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="26"
              height="26"
              fill="currentColor"
              class="bi bi-plus"
              viewBox="0 0 16 16"
            >
              <path
                d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import SectionHeader from "./SectionHeader.vue";
import { ref, onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
// import { start } from "repl";
gsap.registerPlugin(ScrollTrigger);

let more = ref(false);

const mediaQuery = window.matchMedia("(max-width: 800px)");
function handleTabletChange(e) {
  e.matches ? (more.value = false) : (more.value = true);
}

// Register event listener
mediaQuery.addEventListener("change", handleTabletChange);

// Initial check
handleTabletChange(mediaQuery);

function openTab(link) {
  window.open(`${link}`, "_blank");
}

function toggleLoadMore() {
  more.value = !more.value;
  more.value
    ? (document.querySelector(".load-more p").innerHTML = "SEE LESS")
    : (document.querySelector(".load-more p").innerHTML = "SEE MORE");

  gsap.to(".projects", {
    height: "auto",
    duration: 2,
  });
}

onMounted(() => {
  gsap.set(".projects .project", {
    y: "50%",
    zIndex: 1,
    opacity: 0,
  });
  // const workTl = gsap.timeline({});

  gsap.to(".projects .project", {
    y: "0%",
    stagger: {
      amount: 1,
    },
    opacity: 1,
    scrollTrigger: {
      trigger: ".projects .project",
      start: "top bottom-=100",
      end: "bottom top+=300",
      scrub: true,
    },
  });
});
</script>

<style lang="scss" scoped></style>

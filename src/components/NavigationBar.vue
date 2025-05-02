<template>
  <div>
    <!-- Social Blocks -->
    <nav
      class="z-50 fixed flex items-center justify-center gap-4 bottom-10 left-1/2 transform -translate-x-1/2 right-0 md:left-auto lg:right-4 md:top-[50%] lg:top-[50%] flex-row md:flex-col lg:flex-col mx-auto md:translate-x-0 lg:translate-x-0 translate-y-1/2 md:translate-y-[-50%] lg:translate-y-[-50%] lg:translate-x-[-50%] md:translate-x-[-50%]"
    >
      <!-- Home Button -->
      <div class="group relative flex flex-col items-center">
        <span
          class="absolute bg-orange text-white top-[-40px] opacity-0 text-center group-hover:opacity-100 transition-opacity duration-300 px-3 py-1 rounded-md shadow-md text-sm md:text-sm lg:text-sm"
          >Home
        </span>
        <a
          @click="scrollToSection('#home')"
          :class="{
            'text-orange': activeSection === '#home',
            'text-white': activeSection !== '#home',
          }"
          class="cursor-pointer"
        >
          <Icon
            icon="ion:home"
            data-aos="fade-left"
            data-aos-delay="0"
            class="bg-gray-900 w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none"
          />
        </a>
      </div>

      <!-- About Button -->
      <div class="group relative flex flex-col items-center">
        <span
          class="absolute bg-orange text-white top-[-40px] opacity-0 text-center group-hover:opacity-100 transition-opacity duration-300 px-3 py-1 rounded-md shadow-md text-sm md:text-sm lg:text-sm"
          >About</span
        >
        <a
          @click="scrollToSection('#about')"
          :class="{
            'text-orange': activeSection === '#about',
            'text-white': activeSection !== '#about',
          }"
          class="cursor-pointer"
        >
          <Icon
            icon="weui:me-filled"
            data-aos="fade-left"
            data-aos-delay="200"
            class="bg-gray-900 w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none"
          />
        </a>
      </div>

      <!-- Skills Button -->
      <div class="group relative flex flex-col items-center">
        <span
          class="absolute bg-orange text-white top-[-40px] opacity-0 text-center group-hover:opacity-100 transition-opacity duration-300 px-3 py-1 rounded-md shadow-md text-sm md:text-sm lg:text-sm"
          >Skills</span
        >
        <a
          @click="scrollToSection('#skills')"
          :class="{
            'text-orange': activeSection === '#skills',
            'text-white': activeSection !== '#skills',
          }"
          class="cursor-pointer"
        >
          <Icon
            icon="game-icons:skills"
            data-aos="fade-left"
            data-aos-delay="200"
            class="bg-gray-900 w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none"
          />
        </a>
      </div>

      <!-- Experience Button -->
      <div class="group relative flex flex-col items-center">
        <span
          class="absolute bg-orange text-white top-[-40px] opacity-0 text-center group-hover:opacity-100 transition-opacity duration-300 px-3 py-1 rounded-md shadow-md text-sm md:text-sm lg:text-sm"
          >Experience</span
        >
        <a
          @click="scrollToSection('#experience')"
          :class="{
            'text-orange': activeSection === '#experience',
            'text-white': activeSection !== '#experience',
          }"
          class="cursor-pointer"
        >
          <Icon
            icon="icon-park-solid:handbag"
            data-aos="fade-left"
            data-aos-delay="200"
            class="bg-gray-900 w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none"
          />
        </a>
      </div>

      <!-- Contact Button -->
      <div class="group relative flex flex-col items-center">
        <span
          class="absolute bg-orange text-white top-[-40px] opacity-0 text-center group-hover:opacity-100 transition-opacity duration-300 px-3 py-1 rounded-md shadow-md text-sm md:text-sm lg:text-sm"
          >Contact</span
        >
        <a
          @click="scrollToSection('#contact')"
          :class="{
            'text-orange': activeSection === '#contact',
            'text-white': activeSection !== '#contact',
          }"
          class="cursor-pointer"
        >
          <Icon
            icon="ooui:message"
            data-aos="fade-left"
            data-aos-delay="200"
            class="bg-gray-900 w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none"
          />
        </a>
      </div>
    </nav>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";
import { gsap } from "gsap";
import { Icon } from "@iconify/vue";
import { ScrollToPlugin } from "gsap/ScrollToPlugin";

// Register GSAP's ScrollToPlugin
gsap.registerPlugin(ScrollToPlugin);

const activeSection = ref("#home"); // Default active section

// Scroll to the section when the button is clicked
const scrollToSection = (sectionId: string) => {
  const section = document.querySelector(sectionId);
  if (section) {
    const navbarHeight = document.querySelector("header")?.clientHeight || 0; // Get the navbar height
    const targetPosition =
      section.getBoundingClientRect().top + window.scrollY - navbarHeight;

    gsap.to(window, {
      duration: 1.5, // Duration of scroll (1.5 seconds)
      scrollTo: {
        y: targetPosition,
        autoKill: false, // Prevent GSAP from killing the scroll if the user scrolls
      },
      ease: "power2.inOut", // Easing function for smooth animation
    });

    activeSection.value = sectionId; // Set the active section when clicked
  }
};

// IntersectionObserver to track which section is in view
const observerOptions = {
  rootMargin: "-50% 0px", 
};

const observerCallback = (entries: IntersectionObserverEntry[]) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      activeSection.value = `#${entry.target.id}`; // Update active section when it's in view
    }
  });
};

onMounted(() => {
  const observer = new IntersectionObserver(observerCallback, observerOptions);
  
  const sections = document.querySelectorAll("section");
  sections.forEach((section) => observer.observe(section)); // Observe each section

  // Cleanup observer on unmount
  onBeforeUnmount(() => observer.disconnect())
});
</script>


<style scoped>
/* Optional: Add transition effects for navbar buttons */
.navbar-button {
  transition: color 0.3s ease;
}

.text-orange {
  color: #f97316; /* Your orange color */
}
</style>

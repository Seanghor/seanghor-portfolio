<template>
  <section class="text-white max-w-[1440px] mx-auto px-6 md:px-24 lg:px-24 py-12">
    <div class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-2">
      <!-- first -->
      <div data-aos="zoom-in-down" class="grid grid-rows-2 pr-0 lg:pr-16">
        <div>
          <div data-aos="zoom-in-down" class="breathing-effect mb-10 h-10 w-10 lg:h-14 lg:w-14 shadow-lg rounded-full bg-orange flex items-center justify-center">
            <img src="/Logo.png" alt="logo" class="object-contain" />
          </div>
          <p
            class="text-lg md:text-xl lg:text-xl font-semibold leading-normal md:leading-relaxed lg:leading-relaxed"
          >
            Turn your ideas into reality with efficient and scalable web development
            solutions. Let’s create something impactful together.
          </p>
        </div>
        <div
          data-aos="fade-up"
          class="flex flex-col justify-center md:justify-center lg:justify-end"
        >
          <div
            class="grid grid-cols-3 md:grid-cols-5 lg:grid-cols-4 gap-3 md:gap-3 lg:gap-4 justify-between items-end font-semibold text-lg md:text-2xl lg:text-2xl"
          >
            <a @click="scrollToSection('#home')" class="cursor-pointer hover:text-orange"
              >Home.</a
            >
            <a @click="scrollToSection('#about')" class="cursor-pointer hover:text-orange"
              >About</a
            >
            <a
              @click="scrollToSection('#skills')"
              class="cursor-pointer hover:text-orange"
              >Skill.</a
            >
            <a
              @click="scrollToSection('#experience')"
              class="cursor-pointer hover:text-orange"
              >Experience.</a
            >
            <a
              @click="scrollToSection('#contact')"
              class="cursor-pointer hover:text-orange"
              >Contact.</a
            >
          </div>
        </div>
      </div>
      <!-- second -->
      <div class="grid grid-rows-2">
        <!-- Group wrapper with a single trigger -->
        <div data-aos="flip-up" class="grid grid-rows-2 gap-y-0 md:gap-y-6 lg:gap-y-10">
          <div>
            <h4
              data-aos="flip-up"
              data-aos-delay="0"
              class="font-semibold text-h4-sm md:text-h4-md lg:text-h4-lg mb-3 uppercase"
            >
              Contact Me
            </h4>
            <div class="text-textGray text-xs md:text-base lg:text-base">
              <p data-aos="flip-up" data-aos-delay="100">
                <a href="tel:+855967827020" class="hover:underline">
                  +855 (0) 96 782 7020
                </a>
              </p>
              <p data-aos="flip-up" data-aos-delay="200">
                <a href="mailto:hsh.haiseanghor@gmail.com" class="hover:underline">
                  hsh.haiseanghor@gmail.com
                </a>
              </p>
            </div>
          </div>

          <!-- You can add a small delay for the second row if you want staggered feel -->
          <div class="grid md:grid-cols-2 lg:grid-cols-2 gap-4" data-aos-delay="200">
            <div>
              <h4
                class="font-semibold text-h4-sm md:text-h4-md lg:text-h4-lg mb-3 uppercase"
              >
                Location
              </h4>
              <span>
                <p class="text-textGray text-xs md:text-base lg:text-base">
                  Phnom Penh, Cambodia
                </p>
              </span>
            </div>
            <div class="text-left md:text-right text-h4-sm md:text-h4-md lg:text-h4-lg">
              <h4 class="font-semibold mb-3 uppercase">Language</h4>
              <span class="flex flex-row my-auto space-x-3 justify-start md:justify-end">
                <p class="text-white font-medium cursor-pointer hover:scale-105">EN</p>
                <p class="text-textGray font-medium cursor-progress">KH</p>
                <p class="text-textGray font-medium cursor-progress">JP</p>
                <p class="text-textGray font-medium cursor-progress">CH</p>
              </span>
            </div>
          </div>
        </div>

        <div
          class="flex flex-row justify-between items-center md:items-center lg:items-end"
        >
          <div class="flex items-end">
            <div class="grid grid-rows-2 grid-flow-col gap-3">
              <!-- linkied -->
              <div>
                <a
                  :href="socailData.linkedin.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'linkedin']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>

              <!-- github -->
              <div>
                <a
                  :href="socailData.github.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'github']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>
              <!-- telegram -->
              <div>
                <a
                  :href="socailData.telegram.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'telegram']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                /></a>
              </div>
              <!-- facebook -->
              <div>
                <a
                  :href="socailData.facebook.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'facebook']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>

              <!-- wahtsapp -->
              <div>
                <a
                  :href="socailData.whatsApp.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'whatsapp']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>
              <!-- Messanger -->
              <div>
                <a
                  :href="socailData.messanger.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'facebook-messenger']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>

              <!-- Email -->
              <div>
                <a :href="socailData.email.url" target="_blank" rel="noopener noreferrer">
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fas', 'envelope']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>
              <!-- instagram -->
              <div>
                <a
                  :href="socailData.instagram.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <font-awesome-icon
                    data-aos="fade-left"
                    data-aos-delay="0"
                    :icon="['fab', 'instagram']"
                    class="w-5 md:w-5 lg:w-6 h-5 md:h-5 lg:h-6 text-orange flex items-center justify-center rounded-full border border-orange p-1.5 md:p-2 lg:p-2 transition-all transform hover:scale-110 active:scale-95 hover:bg-orange hover:text-white focus:outline-none cursor-pointer"
                  />
                </a>
              </div>
            </div>
          </div>
          <div class="flex flex-col">
            <div class="text-left text-textGray text-xs md:text-base lg:text-base">
              <p>© 2025 Seanghor Hai.</p>
              <p>All rights reserved.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Icon } from "@iconify/vue";
import { socail } from "../../data/socail";
import { ref } from "vue";
import { gsap } from "gsap";
import { ScrollToPlugin } from "gsap/ScrollToPlugin";
const socailData = ref(socail);

// Register GSAP's ScrollToPlugin
gsap.registerPlugin(ScrollToPlugin);
const activeSection = ref("#home"); // Default active section
// Function to animate scrolling to a section
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
</script>

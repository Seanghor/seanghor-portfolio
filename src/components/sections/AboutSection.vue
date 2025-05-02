<template>
  <section class="mb-10 md:mb-20 lg:mb-32">
    <div
      id="about"
      class="text-white max-w-[1440px] mx-auto px-6 md:px-24 lg:px-24 large:px-0 w-screen pt-10 pb-10 md:pb-10 lg:pb-20"
    >
      <!-- Header Section (moves below the image on small screens) -->
      <div
        data-aos="zoom-in"
        class="flex justify-center col-span-full md:col-span-3 lg:col-span-2 inline-block mx-auto mb-10 md:mb-10 lg:mb-10"
      >
        <div>
          <h1 class="text-sm-title md:text-md-title lg:text-lg-title font-bold">
            About <span class="font-semibold text-orange">Me</span>
          </h1>
          <div class="space-y-1 md:space-y-1 lg:space-y-1.5">
            <div class="h-[2px] md:h-[3px] lg:h-[3px] rounded-md bg-orange w-full" />
            <div class="h-[2px] md:h-[3px] lg:h-[3px] mx-2 rounded-md bg-orange" />
          </div>
        </div>
      </div>

      <!-- content -->
      <div
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-10 lg:gap-12"
      >
        <!-- Image Section -->
        <div
          data-aos="fade-up"
          class="col-span-full md:col-span-1 lg:col-span-1 row-span-full lg:row-span-7"
        >
          <img
            src="/aboutme.JPG"
            alt="About Me"
            class="shadow-lg rounded-md w-full h-auto object-cover"
          />
        </div>

        <!-- Paragraph Section -->
        <div class="col-span-full md:col-span-2 lg:col-span-2">
          <div>
            <h6
              data-aos="fade-up"
              class="text-h3-sm md:text-h3-md lg:text-h3-lg font-semibold text-primary"
            >
              Coding is my passion
            </h6>
            <div
              data-aos="fade-up"
              class="whitespace-normal mt-2 text-wrap w-full text-left"
            >
              <p class="leading-relaxed md:leading-relaxed lg:leading-relaxed">
                Coding is my passion, and I thrive on solving complex problems and
                building impactful solutions. I am driven by the challenge of transforming
                abstract ideas into functional, efficient, and scalable systems. My
                journey as a developer is fueled by a deep curiosity to learn new
                technologies and improve the systems I work on. Whether it's designing
                seamless user experiences, optimizing performance, or tackling backend
                complexities, I am dedicated to crafting solutions that deliver real
                value. Every line of code I write is an opportunity to innovate and make a
                positive impact through technology.
              </p>
            </div>
          </div>
        </div>

        <!-- Contact Section (moves to the right of the image on medium screens) -->
        <div
          class="col-span-full md:col-span-2 lg:col-span-2 md:row-start-1 lg:row-start-auto pl-0 md:pl-10 lg:pl-0"
        >
          <div
            class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-2 flex-col text-xs md:text-base lg:text-lg gap-4 md:gap-6 lg:gap-8"
          >
            <!-- DOB -->
            <div
              data-aos="fade-left"
              data-aos-delay="150"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="hugeicons:student" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-medium text-white"> Bachelor:</span>
                <span class="ml-2">Software Engineering</span>
              </p>
            </div>

            <!-- Address -->
            <div
              data-aos="fade-left"
              data-aos-delay="300"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="mdi:location" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-semibold text-white">Address:</span>
                <span class="ml-2">Phnom Penh, Cambodia</span>
              </p>
            </div>

            <!-- Email -->
            <div
              data-aos="fade-left"
              data-aos-delay="350"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="ic:outline-email" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-semibold text-white">Email:</span>
                <span class="ml-2">
                  <a href="mailto:hsh.haiseanghor@gmail.com" class="hover:underline">
                    hsh.haiseanghor@gmail.com
                  </a>
                </span>
              </p>
            </div>

            <!-- Phone -->
            <div
              data-aos="fade-left"
              data-aos-delay="350"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="majesticons:phone-dial-line" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-semibold text-white">Phone:</span>
                <span>
                  <a href="tel:+855967827020" class="hover:underline">
                    +855 (0) 96 782 7020
                  </a>
                </span>
              </p>
            </div>

            <!-- Language -->
            <div
              data-aos="fade-left"
              data-aos-delay="250"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="mdi:spoken-language" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-semibold text-white">Language:</span>
                <span class="ml-2">Khmer, English</span>
              </p>
            </div>

            <!-- Telegram -->
            <div
              data-aos="fade-left"
              data-aos-delay="400"
              data-aos-duration="600"
              data-aos-easing="ease-in-out"
              class="flex items-center gap-3 p-3 rounded-lg shadow-md border-[1px] border-orange"
            >
              <Icon icon="basil:telegram-solid" class="text-orange w-7 h-7" />
              <p class="text-gray-200">
                <span class="font-semibold text-white">Telegram:</span>
                <a
                  href="https://t.me/h_seanghor"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="ml-2 text-gray-200"
                  >@h_seanghor</a
                >
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      data-aos="fade-right"
      data-aos-delay="150"
      data-aos-duration="800"
      data-aos-easing="ease-in-out"
      class="mt-auto mx-auto w-full flex items-center justify-center"
    >
      <div class="bg-orange h-[1px] rounded-md w-[60%] md:w-[40%] lg:w-[40%]"></div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Icon } from "@iconify/vue";
</script>

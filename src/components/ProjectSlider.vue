<template>
  <div
    class="bg-black w-full h-full lg:h-[720px] flex-row py-4 md:py-20 lg:py-20 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-10 md:gap-8 lg:gap-10"
  >
    <!-- left sides -->
    <div
      class="order-last md:order-first lg:order-first flex flex-col justify-between h-full"
    >
      <!-- index and role -->
      <div>
        <div>
          <h1
            data-aos="fade-right"
            class="text-orange text-6xl md:text-8xl lg:text-9xl font-Angkor font-bold"
          >
            {{ projectCode }}
          </h1>
          <h2
            data-aos="fade-left"
            class=" font-bold text-primary text-sm-h2 md:text-md-h2 lg:text-lg-h2"
          >
            {{ title }}
          </h2>
          <div
            class="flex justify-between flex-col md:flex-row lg:flex-row items-start md:items-center lg:items-center gap-1 md:gap-2 lg:gap-2"
          >
            <p
              data-aos="fade-up"
              class="text-textGray font-normal text-base md:text-lg lg:text-lg"
            >
              {{ roleAs }}
            </p>
            <!-- Date range -->
            <p
              data-aos="fade-up"
              data-aos-delay="100"
              class="text-textGray font-normal text-xs md:text-base lg:text-xs"
            >
              <span class="font-semibold">From:</span> {{ startDate }}
              <span class="font-semibold">To:</span> {{ endDate }}
            </p>
          </div>
        </div>
        <div class="my-3 md:my-5 lg:my-">
          <p
            data-aos="fade-up"
            class="whitespace-pre-line leading-relaxed md:leading-relaxed lg:leading-relaxed text-sm md:text-lg lg:text-lg text-textGray font-normal"
          >
            {{ short_desc }}
          </p>
        </div>
      </div>

      <!-- ------------------------- -->
      <div data-aos="fade-left" class="py-10">
        <!-- Technologies -->
        <div class="flex flex-wrap gap-4 ">
          <!-- Display technologies in the desired format -->
          <span
            class="flex items-center font-medium text-base cursor-pointer"
            v-for="(tech, index) in technologies"
            :key="tech.name"
          >
            <img
              :src="tech.icon?.logo"
              :alt="tech.name"
              class="w-4 md:w-5 lg:w-5 h-4 md:h-5 lg:h-5 inline-block mr-2 transition-transform transform hover:scale-110 object-cover"
            />
            <span class="text-xs md:text-sm lg:text-sm text-white hover:text-orange transition-colors">{{
              tech.name
            }}</span>
            <span v-if="index < technologies.length - 1" class="mx-2 text-textGray"
              >,</span
            >
          </span>
        </div>

        <!-- divider -->
        <div class="flex-grow border-t border-orange my-2 md:my-3 lg:my-4"></div>

        <!-- git and project detail -->
        <div class="flex flex-row items-center space-x-4">
          <!-- Button 1 -->
          <button
            class="flex items-center justify-center p-2 rounded-full transition-transform transform hover:scale-110 active:scale-95 focus:outline-none"
          >
            <span
              class="inline-flex items-center justify-center w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 bg-grayBtn rounded-full transition-colors hover:bg-gray-500 active:bg-gray-600"
            >
              <Icon
                class="text-orange w-7 md:w-8 lg:w-8 h-7 md:h-8 lg:h-8 transition-transform hover:scale-105"
                icon="tdesign:arrow-right-up"
              />
            </span>
          </button>

          <!-- Button 2 -->
          <a :href="gitHubUrl" target="_blank" rel="noopener noreferrer">
            <button
              class="flex items-center justify-center p-2 rounded-full transition-transform transform hover:scale-110 active:scale-95 focus:outline-none"
            >
              <span
                class="inline-flex items-center justify-center w-10 md:w-12 lg:w-12 h-10 md:h-12 lg:h-12 bg-grayBtn rounded-full transition-colors hover:bg-gray-500 active:bg-gray-600"
              >
                <Icon
                  class="text-orange w-7 md:w-8 lg:w-8 h-7 md:h-8 lg:h-8 transition-transform hover:scale-105"
                  icon="mdi:github"
                />
              </span>
            </button>
          </a>
        </div>
      </div>
    </div>

    <!-- slider -->
    <div class="h-full bg-white md:bg-black lg:bg-black rounded-xl shadow-lg flex justify-center items-center">
      <div id="controls-carousel" class="relative w-full" data-carousel="static">
        <div class="relative flex items-center justify-center overflow-hidden my-auto">
          <Swiper
            class="mySwiper h-full flex justify-center items-center"
            @slideChange="onSlideChange"
            @swiper="onSwiper"
          >
            <SwiperSlide v-for="(project, index) in projects" :key="index">
              <img
                v-if="index === activeIndex"
                :src="project.imageUrl"
                data-aos="zoom-in"
                class="rounded-xl max-w-full md:max-w-[500px]  lg:max-w-[500px] h-[320px] md:h-[500x]  lg:h-[500px] object-cover md:object-container lg:object-contain mx-auto"
                alt="Project Image"
              />
              <!-- <img
                :v-if="index == activeIndex"
                :src="project.imageUrl"
                data-aos="zoom-in"
                class="max-w-[500px] max-h-[500px] object-container mx-auto"
                alt="Project Image"
              /> -->
            </SwiperSlide>
          </Swiper>
        </div>

        <div>
          <button
            @click="slidePrev"
            :disabled="isPrevDisabled"
            type="button"
            class="mt-5 absolute end-14 z-30 flex justify-center bg-orange group focus:outline-none transition-all duration-200 ease-in-out"
            :class="
              isPrevDisabled
                ? 'opacity-30 cursor-not-allowed'
                : 'hover:bg-opacity-65 cursor-pointer active:scale-95'
            "
          >
            <span
              class="inline-flex items-center justify-center w-8 md:w-9 lg:w-10 h-8 md:h-9 lg:h-10 group-hover:bg-opacity-50 group-focus:outline-none"
            >
              <Icon
                icon="ooui:next-rtl"
                class="text-black w-6 md:w-7 lg:w-8 h-6 md:h-7 lg:h-8 transition-transform duration-200 ease-in-out"
              />
              <span class="sr-only">Previous</span>
            </span>
          </button>

          <button
            @click="slideNext"
            :disabled="isNextDisabled"
            type="button"
            class="mt-5 absolute end-0 z-30 flex items-center justify-center bg-orange group focus:outline-none transition-all duration-200 ease-in-out"
            :class="
              isNextDisabled
                ? 'opacity-25 cursor-not-allowed'
                : 'hover:bg-opacity-65 cursor-pointer active:scale-95'
            "
          >
            <span
              class="inline-flex items-center justify-center w-8 md:w-9 lg:w-10 h-8 md:h-9 lg:h-10 group-hover:bg-opacity-50 group-focus:outline-none"
            >
              <Icon
                icon="ooui:next-ltr"
                class="text-black w-6 md:w-7 lg:w-8 h-6 md:h-7 lg:h-8 transition-transform duration-200 ease-in-out"
              />
              <span class="sr-only">Next</span>
            </span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref, onMounted } from "vue";
import { computed } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import { projectsData } from "../data/project";
import type { projectType } from "../types/project.dto";
import { Icon } from "@iconify/vue";

// Reactive variables
const activeIndex = ref<number>(0);
const projectCode = ref<string>("01");
const projects = ref<projectType[]>(projectsData);
const roleAs = ref<string | null>("");
const title = ref<string | null>("");
const gitHubUrl = ref<string>("");
const short_desc = ref<string | null>("");
const technologies = ref<{ name: string; icon: any }[] | []>([{ name: "", icon: "" }]);
const startDate = ref<string>("None");
const endDate = ref<string>("None");
const isPrevDisabled = ref<boolean>(true);
const isNextDisabled = ref<boolean>(false);

// Function to handle slide changes
const onSlideChange = (swiper: any) => {
  activeIndex.value = swiper.activeIndex;
  updateDetails();
};

// Dummy function for Swiper instance (optional)
const onSwiper = (swiper: any) => {
  console.log("Swiper instance:", swiper);
};

// Custom navigation functions
const slidePrev = () => {
  const swiperElement = document.querySelector(".mySwiper") as HTMLElement & {
    swiper: any;
  };
  swiperElement?.swiper.slidePrev();
  updateDetails();
};

const slideNext = () => {
  const swiperElement = document.querySelector(".mySwiper") as HTMLElement & {
    swiper: any;
  };
  swiperElement?.swiper.slideNext();
  updateDetails();
};

// Function to update details based on activeIndex
const updateDetails = () => {
  gitHubUrl.value = projects.value[activeIndex.value]?.gitHubRepo || "";
  technologies.value = projects.value[activeIndex.value]?.technologies || [];
  projectCode.value = projects.value[activeIndex.value]?.code || "";
  roleAs.value = projects.value[activeIndex.value]?.role || "";
  title.value = projects.value[activeIndex.value]?.title || "";
  short_desc.value = projects.value[activeIndex.value]?.short_desc || "";
  isPrevDisabled.value = activeIndex.value === 0;
  isNextDisabled.value = activeIndex.value === projects.value.length - 1;
  startDate.value = projects.value[activeIndex.value]?.startDate || "None";
  endDate.value = projects.value[activeIndex.value]?.endDate || "None";
};

// Set initial values when the component is mounted
onMounted(() => {
  console.log("Component mounted");
  updateDetails();
});
</script>

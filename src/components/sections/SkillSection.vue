<template>
  <section class="mb-10 md:mb-20 lg:mb-32">
    <div
      id="skills"
      class="text-white max-w-[1440px] mx-auto px-6 md:px-24 lg:px-24 large:px-0 pt-10 pb-10 md:pb-10 lg:pb-20"
    >
      <div class="w-full text-white flex flex-col justify-center">
        <div data-aos="zoom-in" class="inline-block flex-col items-center mx-auto">
          <h1 class="text-sm-title md:text-md-title lg:text-lg-title font-bold">
            My <span class="text-orange">Skills</span>
          </h1>
          <div class="space-y-1 md:space-y-1 lg:space-y-1.5">
            <div class="h-[2px] md:h-[3px] lg:h-[4px] rounded-md bg-orange w-full" />
            <div class="h-[2px] md:h-[3px] lg:h-[4px] mx-2 rounded-md bg-orange" />
          </div>
        </div>

        <!-- text -->
        <div class="mt-8 md:mt-10 lg:mt-12">
          <h3
            data-aos="fade-up"
            class="text-h3-sm md:text-h3-md lg:text-h3-lg font-semibold"
          >
            Skills Reflects Our Knowledge
          </h3>
          <p
            data-aos="fade-up"
            data-aos-delay="100"
            class="mt-4 md:mt-6 lg:mt-8 leading-relaxed md:leading-relaxed lg:leading-relaxed"
          >
            I am a skilled developer with a passion for building efficient, scalable, and
            user-friendly applications. I excel in both frontend and backend development,
            creating seamless user experiences and robust backend systems. With expertise
            in API design, performance optimization, and modern web technologies, I focus
            on delivering high-quality solutions. My goal is to solve complex problems and
            build impactful, reliable software.
          </p>
        </div>

        <!-- Skill Cards Section -->
        <div
          data-aos="zoom-in-up"
          data-aos-delay="200"
          class="overflow-hidden mt-8 md:mt-10 lg:mt-12 rounded-xl mx-auto flex flex-wrap justify-center gap-y-4 md:gap-y-7 lg:gap-y-8 gap-x-5 md:gap-x-5 lg:gap-x-7 px-auto md:px-4 lg:px-5 py-4 md:py-6 lg:py-8"
        >
          <SkillCard
            v-for="(skill, index) in mySkills"
            :key="index"
            data-aos="fade-left"
            :data-aos-delay="index * 150"
            data-aos-duration="600"
            data-aos-easing="ease-in-out"
            :icon="skill.icon"
            :title="skill.name"
          />
        </div>
      </div>
    </div>
    <div
      data-aos="fade-left"
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
import SkillCard from "../SkillCard.vue";
import { ref } from "vue";
import type { skillType } from "../../types/skill.dto";
import { skillData } from "../../data/skill";
import { onMounted } from "vue";

const mySkills = ref<skillType[]>([]);

const setDataForLoad = () => {
  mySkills.value = skillData;
};

onMounted(() => {
  setDataForLoad();
});
</script>

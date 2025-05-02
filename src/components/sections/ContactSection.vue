<template>
  <section
    id="contact"
    class="text-white max-w-[1440px] mx-auto px-6 md:px-24 lg:px-24 pt-20 pb-10 md:pb-10 lg:pb-20"
  >
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-10 items-start">
      <!-- Left side -->
      <div class="w-full text-lg leading-relaxed">
        <h2
          data-aos="fade-up"
          class="font-bold text-orange text-3xl md:text-4xl text-center md:text-left lg:text-left mb-8 md:mb-8 lg:mb-14"
        >
          Get in Touch
        </h2>
        <p
          data-aos="flip-up"
          class="text-lg md:text-xl lg:text-xl mb-4 md:mb-8 lg:mb-10 text-gray-300 pr-0 md:pr-8 lg:pr-10 font-medium leading-normal"
        >
          Feel free to get in touch by filling out the form. I'm here to assist with any
          questions or inquiries you may have, and I look forward to connecting with you!
        </p>
      </div>

      <!-- Form -->
      <div class="rounded-lg">
        <form @submit.prevent="sendEmail" data-aos="zoom-in" class="space-y-5">
          <!-- Email -->
          <div class="flex items-center border-b border-orange py-2">
            <input
              class="appearance-none focus:ring-black bg-transparent border-none w-full text-white mr-3 py-1 px-2 leading-tight focus:outline-none"
              v-model="email"
              type="email"
              id="email"
              placeholder="example@gmail.com"
              aria-label="Email Address"
              required
            />
          </div>

          <!-- Subject -->
          <div class="flex items-center border-b border-orange py-2">
            <input
              class="appearance-none focus:ring-black bg-transparent border-none w-full text-white mr-3 py-1 px-2 leading-tight focus:outline-none"
              v-model="subject"
              type="text"
              id="subject"
              required
              placeholder="Subject"
            />
          </div>

          <!-- Message -->
          <div class="flex items-center border-b border-orange py-2">
            <textarea
              placeholder="Message"
              rows="6"
              class="appearance-none focus:ring-black bg-transparent border-none w-full text-white mr-3 py-1 px-2 leading-tight focus:outline-none"
              v-model="message"
              id="message"
              required
            ></textarea>
          </div>

          <!-- Submit Button -->
          <div class="text-center flex justify-end items-end">
            <button
              type="submit"
              class="text-whiteLight text-sm-btn md:text-md-btn lg:text-lg-btn uppercase bg-orange hover:bg-orange-600 flex justify-center items-center rounded-sm py-2 px-5 md:py-3 md:px-7 lg:py-3 transition-all duration-500 transform hover:scale-105 shadow-lg"
            >
              Submit
            </button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from "vue";

const email = ref("");
const subject = ref("");
const message = ref("");

const sendEmail = () => {
  const to = "hsh.haiseanghor@gmail.com";

  const encodedSubject = encodeURIComponent(subject.value);
  const encodedMessage = encodeURIComponent(message.value);

  const mailtoLink = `https://mail.google.com/mail/u/0/?source=mailto&to=${to}&subject=${encodedSubject}&body=${encodedMessage}&fs=1&tf=cm`;

  // Open the mailto link in a new tab
  window.open(mailtoLink, "_blank");
};
</script>

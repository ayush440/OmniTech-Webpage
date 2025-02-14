<template>
  <section class="relative w-full h-[450px] md:h-full xl:h-[500px] overflow-hidden xl:bg-[#e8f1f2]">
    <!-- Blurred Gradient Background -->
    <div class="absolute inset-0 flex items-center justify-center">
      <div class="w-[350px] h-[350px] xl:w-[1000px] bg-radial-gradient opacity-60 md:opacity-50 blur-3xl transform -translate-y-20"></div>
    </div>

    <div class="relative px-4 md:px-6 ">
      <div class="max-w-7xl mx-auto">
        <!-- Main Hero Section -->
        <div class="items-center relative z-10">
          <!-- Left Content -->
          <div class="space-y-6 md:pl-8 max-w-5xl ">
            <p class="text-sm text-gray-600 font-medium mt-10 hidden md:block ">Trade without the stress let the algo decide!            </p>
            <h1 class="text-4xl md:text-5xl xl:text-[70px] lg:text-[82px] font-bold text-gray-900 text-center md:text-left leading-[1.2] md:leading-[1.1] xl:leading-[1.2]">
              Why trade manually when the algo can handle it seamlessly?
            </h1>

            <p class="text-gray-600 max-w-4xl text-lg text-center md:text-left ">
              Battling emotions, missing opportunities, and constantly watching the market manually. Let automation handle the complexity while you focus on what truly matters. Stay ahead, trade smarter, and let the algorithm work for you!
            </p>
            <button class="px-8 py-3  bg-[#21A5F0] text-white rounded-md hover:bg-[#6A35C2] transition-colors duration-200 font-medium text-lg flex justify-center items-center mx-auto md:mx-0">
              Join Now
            </button>
          </div>
        </div>

        <!-- Stats Card -->
         
       
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const count1 = ref(0)
const count2 = ref(0)
const count3 = ref(0)

const formatNumber = (num) => {
  return new Intl.NumberFormat().format(num)
}

const animateValue = (target, duration, element) => {
  const start = 0
  const increment = (target / duration) * 10
  let current = 0

  const timer = setInterval(() => {
    current += increment
    if (current >= target) {
      element.value = target
      clearInterval(timer)
    } else {
      element.value = Math.round(current * 100) / 100
    }
  }, 10)
}

onMounted(() => {
  animateValue(30, 2000, count1)
  animateValue(5000, 2000, count2)
  animateValue(90.99, 2000, count3)
})
</script>

<style>
.bg-radial-gradient {
  background: radial-gradient(
    circle at center,
    #D798E1 0%,
    #9BFFA5 25%,
    #AED3FF 50%,
    #C9D4EF 75%,
    #CACFFA 100%
  );
}
</style>
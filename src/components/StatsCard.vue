<template>
  <div class="bg-[#f2f0fa] backdrop-blur-sm rounded-3xl mt-16  p-6 max-w-6xl w-full mx-auto relative z-10">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
      <!-- Left Content -->
      <div class="lg:col-span-5">
        <p class="text-sm text-gray-600 font-medium">Let AI Do the Work!</p>
        <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mt-2 leading-tight ">
          “The future of trading isn’t human - AI is transforming markets and trading the future today.”

        </h2>
      </div>

      <!-- Stats -->
      <div class="lg:col-span-4">
        <div class="grid grid-cols-1 gap-8">
          <div>
            <h3 class="text-3xl font-extrabold text-gray-900">
              {{ count1 }}+
            </h3>
            <p class="text-gray-600 mt-1">Customizable Strategies</p>
          </div>
          <div>
            <h3 class="text-3xl font-extrabold text-gray-900">
              {{ formatNumber(count2) }}+
            </h3>
            <p class="text-gray-600 mt-1">Active Users</p>
          </div>
          <div>
            <h3 class="text-3xl font-extrabold text-gray-900">
              {{ count3 }}%
            </h3>
            <p class="text-gray-600 mt-1">Trade Execution Accuracy</p>
          </div>
        </div>
      </div>

      <!-- Image -->
       <div class="lg:col-span-3 bg-white rounded-lg relative min-w-60 ">
        <img 
          src="../assets/img/professional.webp" 
          alt="Professional trader" 
          class=" absolute  hidden xl:block transform scale-125 -translate-x-10 -translate-y-64"
        />
      </div> 
    </div>
  </div>
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

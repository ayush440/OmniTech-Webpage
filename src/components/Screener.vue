<template>
  <Navbar />
  <div class=" absolute z-50 justify-center items-center w-full py-96 mb-10 hidden xl:flex">
    <StatsCard />
  </div>
  <Tutorial />
  <div class="  justify-center items-center w-full md:mt-10 mb-10 flex xl:hidden">
    <StatsCardMobile />
  </div>
  <Comparison />
  <Globe />
  <Cards />
  <!-- <Modal /> -->
  <Report />
  <Invoice />
  <Features id="features" />
  <Why id="why" />

  <Footer />
</template>

<script setup>
import Features from "./Features.vue";
import Tutorial from "./Tutorial.vue";
import Why from "./Why.vue";
import Navbar from "./Navbar.vue";
import Footer from "./Footer.vue";
import Comparison from "./Comparison.vue";
import Globe from "./Globe.vue";
import Cards from "./Cards.vue";

// import Feedback from "./StatsCard.vue";
import StatsCard from "./StatsCard.vue";
import StatsCardMobile from "./StatsCardMobile.vue";// Import StatsCard Component
import Modal from "./Modal.vue";
import Report from "./Report.vue";
import Invoice from "./Invoice.vue";

</script>

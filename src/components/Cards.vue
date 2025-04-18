<template>
  <section class="bg-gradient-to-br from-[#f3f3f3] to-[#f5f9fa] py-20 relative overflow-hidden">
    <!-- Gradient Circle -->
    <img 
      src="../assets/img/Gradient.png" 
      alt="Gradient Background" 
      class="absolute hidden xl:block"
    />
    
    <div class="container mx-auto px-4 lg:px-16 max-w-7xl">
      <div class="flex flex-col lg:flex-row gap-12">
        <!-- Left Column -->
        <div class="max-w-xl w-full xl:ml-10 relative mx-auto">
          <div class="relative z-10"> 
            <h2 class="text-2xl md:text-4xl font-extrabold text-gray-900 mb-6 text-center xl:text-left">
              The Ultimate Trading Features for Market Mastery
            </h2>
            <p class="text-gray-600 mb-8 text-center xl:text-left">
              Explore the power of intelligent trading with features designed for precision, speed, and seamless automation.
            </p>
          </div>
        
          <button class="bg-[#21A5F0] text-white px-8 py-4 rounded-md font-medium transition-colors flex justify-center items-center mx-auto xl:mx-0">
            Join Now
          </button>
          <!-- Background Radial Gradient -->
          <div class="absolute inset-0 flex md:hidden items-center justify-center">
            <div class="w-[350px] h-[350px] xl:w-[1000px] bg-radial-gradient opacity-50 md:opacity-50 blur-3xl transform -translate-y-20"></div>
          </div>
        </div>

        <!-- Right Column - Features Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 w-full">
          <!-- Smart Strategy Builder -->
          <div class="bg-white rounded-xl p-6 shadow-sm flex flex-col">
            <div class="mb-4 flex items-center justify-start h-16">
              <div ref="marketAnalysisAnimation" class="w-16 h-16"></div>
            </div>
            <h3 class="text-lg font-bold text-gray-900 mb-2">
              Real-Time Market Analysis
            </h3>
            <p class="text-gray-600 flex-grow">
              Leverage AI-driven insights that continuously scan the markets, identifying profitable opportunities and executing trades at the perfect moment.
            </p>
          </div>

          <!-- Instant Alerts -->
          <div class="bg-white rounded-xl p-6 row-span-2 pt-16 shadow-sm flex flex-col">
            <div class="mb-4 flex items-center justify-start h-16">
              <div ref="riskManagementAnimation" class="w-16 h-16"></div>
            </div>
            <h3 class="text-lg font-bold text-gray-900 mb-2 flex items-center">
              Risk Management Controls
            </h3>
            <p class="text-gray-600 flex-grow">
              Minimize potential losses with automated stop-loss, take-profit, and position-sizing strategies, ensuring disciplined and secure trading.
            </p>
          </div>

          <!-- AI-Powered Market Insights -->
          <div class="bg-white rounded-xl p-6 row-span-2 pt-16 shadow-sm flex flex-col">
            <div class="mb-4 flex items-center justify-start h-16">
              <div ref="multiAssetsAnimation" class="w-16 h-16"></div>
            </div>
            <h3 class="text-lg font-bold text-gray-900 mb-2">
              Multi-Asset Trading
            </h3>
            <p class="text-gray-600 flex-grow">
              Trade across various markets, including stocks, options, forex, and crypto, all from a single platform, optimizing diversification and efficiency.
            </p>
          </div>

          <!-- Auto-Execution -->
          <div class="bg-white rounded-xl p-6 shadow-sm flex flex-col">
            <div class="mb-4 flex items-center justify-start h-16">
              <div ref="backtestingAnimation" class="w-16 h-16"></div>
            </div>
            <h3 class="text-lg font-bold text-gray-900 mb-2">
              Backtesting & Optimization
            </h3>
            <p class="text-gray-600 flex-grow">
              Test and refine your trading strategies using historical data, allowing you to optimize performance before deploying them in live markets.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from 'vue';
import lottie from 'lottie-web';

export default {
  name: 'TradingFeaturesSection',
  setup() {
    const marketAnalysisAnimation = ref(null);
    const riskManagementAnimation = ref(null);
    const multiAssetsAnimation = ref(null);
    const backtestingAnimation = ref(null);

    const loadAnimation = (container, path) => {
      try {
        lottie.loadAnimation({
          container: container.value,
          renderer: 'svg',
          loop: true,
          autoplay: true,
          path: path,
          onError: (error) => {
            console.error(`Error loading animation from ${path}:`, error);
          },
        });
      } catch (error) {
        console.error('Error initializing animation:', error);
      }
    };

    onMounted(() => {
      
      loadAnimation(marketAnalysisAnimation, '/src/assets/json/market-analysis.json');
      loadAnimation(riskManagementAnimation, '/src/assets/json/risk-management.json');
      loadAnimation(multiAssetsAnimation, '/src/assets/json/multi-assets.json');
      loadAnimation(backtestingAnimation, '/src/assets/json/backtesting.json');
    });

    return {
      marketAnalysisAnimation,
      riskManagementAnimation,
      multiAssetsAnimation,
      backtestingAnimation
    };
  }
};
</script>






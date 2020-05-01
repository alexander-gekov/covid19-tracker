<template>
  <div class="tracker-container font-sans w-11/12 lg:w-7/12 overflow-hidden bg-gray-400 shadow-lg rounded-lg">
    <div class="top-image" style="height:200px;">
      <img src="/img/medical.svg" alt="">
    </div>
    <!--    Banner End-->
    <div class="tracker flex h-72">
      <div class="country-container flex flex-1 flex-col overflow-hidden w-1/4 bg-gray-800 text-white">
        <div class="py-2 px-4 bg-gray-900 font-bold text-center">Country</div>
        <div class="countries flex-1 overflow-y-scroll sidebar-countries">
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
          <div class="py-2 px-4 hover:bg-gray-700">USA</div>
          <div class="py-2 px-4 hover:bg-gray-700">Spain</div>
        </div>
      </div>
      <!--      Countries end-->
      <div class="info w-3/4 bg-gray-300">
        <div class="world bg-gray-800 flex justify-between mb-4 text-white pr-6">
          <div class="py-2 px-4 font-bold text-center">World</div>
          <!--          Title End-->
          <div class="flex bg-gray-100 rounded-lg m-2 w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Total:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">130</div>
          </div>
          <div class="flex bg-gray-100 rounded-lg m-2 w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Deaths:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">130</div>
          </div>
          <div class="flex bg-gray-100 rounded-lg m-2 w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Recovered:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">130</div>
          </div>
        </div>
        <!--        World Data end-->
        <div class="total flex px-6 py-4 justify-between mb-4">
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/4 shadow-lg">
            <div class="pb-2 text-center">Total cases:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/4 shadow-lg">
            <div class="pb-2 text-center">Total deaths:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/4 shadow-lg">
            <div class="pb-2 text-center">Total recovered:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
        </div>
        <!--        First row End-->
        <div class="new flex px-16 py-4 justify-around">
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/3 shadow-lg">
            <div class="pb-2 text-center">New cases:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/3 shadow-lg">
            <div class="pb-2 text-center">New deaths:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
        </div>
        <!--        Second Row end-->
        <div class="active flex px-10 py-4 justify-around">
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-1/2 shadow-lg">
            <div class="pb-2 text-center">Active cases:</div>
            <div class="text-center bg-gray-300 rounded-lg">100</div>
          </div>
        </div>
        <!--        Third row end-->
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    mounted() {
      console.log('Component mounted.')
    }
  }
</script>

<style>
  .sidebar-countries::-webkit-scrollbar {
    width: 8px;
    background-color: #2d3748;
  }

  .sidebar-countries::-webkit-scrollbar-thumb {
    border-radius: 8px;
    background-color: #535353;
  }
</style>

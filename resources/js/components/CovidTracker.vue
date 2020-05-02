<template>
  <div class="tracker-container font-sans w-11/12 lg:w-7/12 overflow-hidden bg-gray-400 shadow-lg rounded-lg mb-4">
    <div class="top-image" style="height:200px;">
      <img src="/img/medical.svg" alt="">
    </div>
    <!--    Banner End-->
    <div class="tracker flex h-78 lg:h-72">
      <div class="country-container flex flex-1 flex-col overflow-hidden w-1/3 lg:w-1/4 bg-gray-800 text-white">
        <div class="py-2 px-4 bg-gray-900 font-bold text-center">Country</div>
        <div class="countries flex-1 overflow-y-scroll sidebar-countries">
          <a href="#" @click.prevent="selectCountry(country)" v-for="country in this.countryData"
             class="flex py-2 px-2 hover:bg-gray-700">
            <div class="px-2 py-2">
              <img class="w-8 lg:w-12" :src="country.flag" alt="">
            </div>
            <div class="pt-2 text-sm">{{country.country}}</div>
          </a>
        </div>
      </div>
      <!--      Countries end-->
      <div class="info w-2/3 lg:w-3/4 bg-gray-300">
        <div class="world bg-gray-800 lg:flex justify-between mb-6 text-white pr-16 pb-2">
          <div class="py-2 px-4 font-bold justify-center">World</div>
          <!--          Title End-->
          <div class="flex bg-gray-100 rounded-lg m-2 lg:w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Total:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">{{this.worldData.total_cases}}</div>
          </div>
          <div class="flex bg-gray-100 rounded-lg m-2 lg:w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Deaths:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">{{this.worldData.death_cases}}</div>
          </div>
          <div class="flex bg-gray-100 rounded-lg m-2 lg:w-1/5 shadow-lg text-black justify-between">
            <div class="px-2">Recovered:</div>
            <div class="text-center bg-gray-500 rounded-lg text-right px-2">{{this.worldData.recovery_cases}}</div>
          </div>
        </div>
        <!--        World Data end-->
        <div class="selected-country flex justify-center">
          Selected country: {{this.selectedCountryData.country}}
        </div>
        <!--        End Selected Label-->
        <div class="total lg:flex px-2 lg:px-10 pt-4 lg:pt-16 lg:pb-12 justify-between mb-4">
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-100 lg:w-40 shadow-lg mb-2 ">
            <div class="pb-2 text-center">Total cases:</div>
            <div class="flex align-items-center text-center bg-gray-300 rounded-lg pl-3">
              {{this.selectedCountryData.total_cases}}
              <span v-if="this.selectedCountryData.new_cases!=0" class="py-1 pl-2"><img
                src="/img/uparrow.png" width="10"
                alt=""></span>
              <span v-if="this.selectedCountryData.new_cases!=0" class="text-red-700"><sup>{{this.selectedCountryData.new_cases}}</sup></span>
            </div>
          </div>
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-75 lg:w-1/4 shadow-lg mb-2">
            <div class="pb-2 text-center">Total deaths:</div>
            <div class="flex align-items-center text-center bg-gray-300 rounded-lg pl-3">
              {{this.selectedCountryData.total_deaths}}
              <span v-if="this.selectedCountryData.new_deaths!=0" class="py-1 pl-2"><img
                src="/img/uparrow.png" width="10"
                alt=""></span>
              <span v-if="this.selectedCountryData.new_deaths!=0" class="text-red-700"><sup>{{this.selectedCountryData.new_deaths}}</sup></span>
            </div>
          </div>
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-75 lg:w-1/4 shadow-lg lg:mb-2">
            <div class="pb-2 text-center">Total recovered:</div>
            <div class="text-center bg-gray-300 rounded-lg">{{this.selectedCountryData.total_recovered}}</div>
          </div>
        </div>
        <!--        First row End-->
        <div class="active lg:flex px-2 lg:px-10 justify-around">
          <div class="bg-gray-100 rounded-lg px-2 py-2 w-100 lg:w-1/2 shadow-lg">
            <div class="pb-2 text-center">Active cases:</div>
            <div class="text-center bg-gray-300 rounded-lg">{{this.selectedCountryData.active_cases}}</div>
          </div>
        </div>
        <!--        Second row end-->
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    mounted() {
      axios.get('https://corona-virus-stats.herokuapp.com/api/v1/cases/general-stats')
        .then(response => {
          this.worldData = response.data.data;
          //console.log(response.data.data);
        })
      axios.get('https://corona-virus-stats.herokuapp.com/api/v1/cases/countries-search?limit=206')
        .then(response => {
          this.countryData = response.data.data.rows;
          this.selectedCountryData = response.data.data.rows[1];
          console.log(this.countryData)
        });
    },
    data: function () {
      return {
        worldData: [],
        countryData: [],
        selectedCountry: 'Bulgaria',
        selectedCountryData: [],
      }
    },
    methods: {
      selectCountry: function (country) {
        this.selectedCountryData = country;
        console.log(country)
      }
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

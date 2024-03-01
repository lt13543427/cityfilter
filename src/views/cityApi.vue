<script>
import Cityfilter from '@/components/cityfilter.vue';

export default {
    props: {
        sortCity:[],
    },
  components: {
    Cityfilter,
  },
  data() {
    return {
      inputText: '',
      cityArr: [],
    };
  },
  async mounted() {
    try {
      const api = await fetch('https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json');
      const data = await api.json();
      this.cityArr = data;
    } catch (error) {
      console.error(error);
    }
  },
  computed: {
    sortCity() {
      const inputText = this.inputText.toLowerCase();
      if (inputText !== '') {
        return this.cityArr.filter((item) => {
          return item.city.toLowerCase().includes(inputText);
        });
      }
    },
  },
  methods: {
  },
}
</script>

<template>
  <div class="city-div w-full flex items-center justify-center flex-col">
    <h1 class="text-3xl font-black mt-5">美立堅合眾國城市查詢系統</h1>
    <div class="w-full flex justify-center mt-5">
      <input type="text" class="w-1/3 h-[60px] bg-slate-100 rounded-md" v-model="inputText" placeholder="請輸入城市名(英文)">
    </div>
    <div class="div w-full mt-5 justify-center items-center flex flex-col gap-1">
      <div class="content flex gap-5 rounded-lg" v-for="(item, index) in sortCity" :key="item.city + index">
        城市名:{{ item.city }}<br>人口數:{{ item.population }}
      </div>
    </div>  
    <Cityfilter></Cityfilter>
  </div>
</template>

<style scoped>
.content {
  @apply w-1/3 h-[60px] flex items-center justify-center bg-slate-500 m-auto;
}
</style>

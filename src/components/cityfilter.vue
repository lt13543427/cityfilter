<script>
export default {
    data(){
        return{
            inputText:'',
            cityArr:[]
        }
    },
    // computed:{
    //     filterCity() {
    //         const inputText = this.inputText.toLowerCase();
    //         if(inputText !== ''){
    //             return this.cityArr.filter((item) => {
    //                 return item.city.toLowerCase().includes(inputText);
    //             });
    //         }
    //     },
    // }, 
}
</script>
<template>
  <div class="div w-full mt-5 justify-center items-center flex flex-col gap-1">
      <div class="content flex gap-5 rounded-lg" v-for="(item, index) in filterCity" :key="item.city+index">
      城市名:{{ item.city }}<br>人口數:{{ item.population}}
      </div>
  </div>     
</template>
<style>
</style>
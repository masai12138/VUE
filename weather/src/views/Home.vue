<script>
import axios from 'axios'
export default {
  data: function(){
    return {
      weather: null,
    }
  },
  methods:{
    getCondImage: function(){
      // return require('../assets/' + this.weather.now.cond_code + '.png')
      return require(`../assets/${this.weather.now.cond_code}.png`)
    }
  },
  created: function(){
    console.log("create")

    let that = this
    axios.get('https://free-api.heweather.net/s6/weather/now?location=hangzhou&key=96e8453513a5487c923a71d839a180ca')
    .then(function(response){
      console.log("请求结果",response)
      if(response.status !== 200){
        console.log(response.statusText)
        return;
      }
      let weatherArray = response.data.HeWeather6
      if(!weatherArray || weatherArray.length <= 0){
        console.log('天气数据为空');
        return;
      }
      that.weather = weatherArray[0]
    })
    .catch(function(e){
      console.log("请求失败", e)
    })
  }
}

</script>

<template>
  <div id="app">
    <div class="top" v-if="weather">
      <img class="top-condition-icon" :src="getCondImage()" alt=""/>
      <div><span class="top-temperature">{{weather.now.tmp}}</span></div>
      <span class="top-location">{{weather.basic.location + ',' + weather.basic.cnty}}</span>
    </div>
  </div>
</template>

<style scoped>
.body{
  margin: 0;
  padding: 0;
}
.top{
    display: flex;
    flex-direction: column;
    align-items: center;
    /* justify-content: center; */
    
}
.top-condition-icon{
  width: 50px;
  height: 50px;
  margin: 50px 0 0 0;
}
.top-temperature{
  font-size: 40px;
  line-height: 1;
  text-align: center;
  width: auto;
  margin: 15px 0 0 0;
  float: left;
}
.top-location{
  line-height: 1;
  font-size: 15px;
  margin-top: 10px;
  color: #999;
}


</style>




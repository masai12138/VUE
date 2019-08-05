<script>
import axios from 'axios'
export default {
    data : function(){
        return {
            city : null,
            cityweather : null,
        }
    },
    methods : {
        getcity : function(){
            let that = this
            axios.get('https://free-api.heweather.net/s6/weather/now?&key=96e8453513a5487c923a71d839a180ca&',{
                params:{
                    location : that.city
                }
            })
            .then(function(response){
                console.log(response)
                if(response.status !== 200){
                    console.log(response.statusText)
                    return;
                }
                that.cityweather = response.data.HeWeather6[0]
                
            })
        }
    }
}
</script>

<template>
    <div class="q-main">
        <input class="q-text" type="text" placeholder="请输入想查询城市名称" v-model="city"/>
        <button class="q-sub" @click="getcity()">查询</button>
        <div v-if="cityweather" class="middle-main">
            <img :src="require(`../assets/${this.cityweather.now.cond_code}.png`)"/>
            <span>{{cityweather.now.tmp}}</span>
            <span>{{cityweather.basic.location + ',' + cityweather.basic.cnty}}</span>
        </div>
    </div>
</template>

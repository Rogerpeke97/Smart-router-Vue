<template>
  <div class="hello">
      <div class="data_container">Date
        <div v-for="index in weather" v-bind:key="index" class="dates">
            {{ formatDate(index.dt) }}
        </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'DataDisplay',
  data(){
      return{
      weather: null
      }
  },
  props: {

  },
  mounted(){
      axios.get('https://api.openweathermap.org/data/2.5/onecall?lat=33.44&lon=-94.04&appid=e5612b2fc3f2246e81c603e927091272')
      .then(response=>{
          this.weather = response.data.daily;
      })
      .catch(error=>console.log(error))
  },
  methods: {
      formatDate(unix_date){
          let date = new Date(unix_date * 1000);
          return date.toString();
      }
  }
}
</script>

<style scoped>
.hello{
    width: 100vw;
    background: black;
    color: white;
}
.dates{
    background: rgba(44,12,175,1);
    width: 250px;
    display: grid;
    height: 50px;
    align-items: center;
}
.data_container{
    display: grid;
    justify-items: left;
    text-align: center;
}
</style>
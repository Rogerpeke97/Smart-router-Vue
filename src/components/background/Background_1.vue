<template>
    <div class="background_main">
      <div class="left_side_text">
        <br/><br/><br/><br/><br/><br/><br/><br/><br/>
        <div :style = "styleTitle">
          Using 
          <a href="https://www.okex.com/" rel="noopener noreferrer" target="_blank" class= "font-awesome_nav_bar">
            Okex
          </a>
          API...
        </div>
        <br/><br/>
        Smart Order Routing or shortly SOR is indeed a perfect tool 
        to cope with ever changing prices and liquidity problems. 
        This is an automated tool that helps process orders at the 
        best price available across multiple markets in real time. 
        In order to provide the best offer, it checks the current rate 
        for any selected pair across different exchanges and helps to find 
        the route to make a switch.
        <br/><br/><br/>
        <div class="website_button">Get started!</div>
      </div>
      <div class="right_side_text" v-on:mousemove="transform_carbon">
        <img class="right_side_image" src="carbon.svg" alt="Smart router logo" />
      </div>
      <SideMenu v-bind:showSideMenu="showSideMenu" />
    </div>
</template>


<script>
import SideMenu from './side_menu/SideMenu.vue';
export default {
  name: 'BackgroundOne',
  methods: {
  transform_carbon: function (e) {
      let mousex = (e.clientX   - ( e.currentTarget.getBoundingClientRect().left / 2)) ;
      let mousey = (e.clientY  - ( e.currentTarget.getBoundingClientRect().top / 2)) ;
      let x = mousex - e.currentTarget.getBoundingClientRect().width / 2 ;
      let y = e.currentTarget.getBoundingClientRect().height / 2 - mousey ;
      x = x / 100;
      y = y / 100;
      e.currentTarget.style.transform = `perspective(700px) rotateY(${x - 20}deg) rotateX(${ y + 10}deg)`;
    }
  },
  data(){
    return{
      styleTitle:{
        fontSize: '3rem'
      }
    }
  },
  props: {
    showSideMenu: Boolean
  },
  components:{
    SideMenu
  }
}
</script>


<style scoped>
.background_main {
  background: linear-gradient(-90deg, #02203c, #001528);
  width: 100vw;
  display: flex;
  color: white;
  height: 100vh;
  font-family: 'Ubuntu', sans-serif;
  text-align: justify;
  overflow: hidden;
}
.left_side_text{
  flex: 35%;
  border-radius: 12px;
  background: #001528;
  padding: 1%;
  text-align: justify;
}
.right_side_text{
  flex: 50%;
  object-fit: contain;
  height: 600px;
  display: grid;
  justify-content: center;
  transform: perspective(700px) rotateY(-20deg) rotateX(10deg);
}
.right_side_image{
  max-height: 100%;
  min-height: 100%;
  object-fit: contain;
}
.website_button{
    position: relative;
    width: 130px;
    height: 60px; 
    left: 50%;
    margin-left: -65px;
    background: rgba(44,12,175,1);
    border-radius: 5px;
    color: white;
    font-weight: bold;
    text-shadow: 2px 2px 2px black;
    cursor: pointer;
    text-align: center;
    transition: all 0.5s ease-out;
    display: grid;
    align-items: center;
    z-index: 1;
}
.website_button:hover{
  background: rgb(56, 16, 219);
}
</style>
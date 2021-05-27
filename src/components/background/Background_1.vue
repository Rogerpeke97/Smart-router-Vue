<template>
    <div class="background_main">
      <div class="left_side_text">
        <div :style = "styleTitle">
          Using 
          <a href="https://www.okex.com/" rel="noopener noreferrer" target="_blank" class= "font-awesome_nav_bar">
            Okex
          </a>
          API...
        </div>
        Smart Order Routing or shortly SOR is indeed a perfect tool 
        to cope with ever changing prices and liquidity problems. 
        This is an automated tool that helps process orders at the 
        best price available across multiple markets in real time. 
        In order to provide the best offer, it checks the current rate 
        for any selected pair across different exchanges and helps to find 
        the route to make a switch.
        <div class="website_button">Get started!</div>
      </div>
      <div class="right_side_text" v-on:mousemove="transform_carbon">
        <img class="right_side_image" src="../../../public/carbon.svg" alt="Smart router logo" />
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
        fontSize: '250%',
        marginBottom: '30px'
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
  max-width: 100vw;
  min-width: 100vw;
  display: flex;
  color: white;
  height: 1080px;
  font-family: 'Ubuntu', sans-serif;
  text-align: justify;
  overflow: hidden;
}
.left_side_text{
  flex: 35%;
  padding-top: 350px;
  border-radius: 12px;
  background: #001528;
  padding-left: 1%;
  padding-right: 1%;
  text-align: justify;
}
.right_side_text{
  flex: 50%;
  padding-top: 120px;
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
    margin-top: 65px;
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

@media only screen and (max-width: 890px) {
  .background_main {
    display: grid;
    grid-template-rows: 40% 60%;
  }
  .left_side_text {
    padding-top: 100px;
    padding-right: 2.5%;
  }
  .right_side_text {
    padding-top: 0px;
  }
}
@media only screen and (max-width: 500px) {
  .left_side_text {
    font-size: 70%;
  }
  .right_side_text {
    width: 80%;
    position: relative;
    left: 10%;
  }
  .right_side_image{
    max-width: 100%;
  }
}
</style>
<template>
    <div class="background_main">
      <div class="left_side_text">
        <br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>
        Smart Order Routing or shortly SOR is indeed a perfect tool 
        to cope with ever changing prices and liquidity problems. 
        This is an automated tool that helps process orders at the 
        best price available across multiple markets in real time. 
        In order to provide the best offer, it checks the current rate 
        for any selected pair across different exchanges and helps to find 
        the route to make a switch.
      </div>
      <div class="right_side_text" v-on:mousemove="transform_carbon">
        <img class="right_side_image" src="carbon.svg" alt="Smart router logo" />
      </div>
    </div>
</template>


<script>
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
  }
}
</script>


<style scoped>
.background_main {
  background: linear-gradient(-90deg, #02203c, #001528);
  width: 100vw;
  display: flex;
  color: white;
  height: 700px;
  font-weight: bold;
  font-family: 'Ubuntu', sans-serif;
  text-align: justify;
}
.left_side_text{
  flex: 35%;
  margin-left: 10px;

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
</style>
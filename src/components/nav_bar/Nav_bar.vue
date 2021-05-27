<template>
    <div class="navigation_bar">
        <div class="nav_options_container">
            <div class="nav_option_items">
                {{"SmartRouter"}}
                <img class= "nav_bar_img" src="diamond.png" alt="Smart router logo" />
            </div>
        </div>
        <div class="nav_options_container_right">
            <div class="font-awesome_container">
                <a href="https://github.com/Rogerpeke97" rel="noopener noreferrer" target="_blank" class= "font-awesome_nav_bar">
                    <font-awesome-icon :icon = "['fab', 'github']" class= "font-awesome_nav_bar" />
                </a>
            </div>
            <div class="font-awesome_container">
                <div class="hamburguer" v-bind:class="{'open': bool}" @click="setShow()" >
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faUserSecret, faBars } from '@fortawesome/free-solid-svg-icons'
import {faGithub} from '@fortawesome/free-brands-svg-icons'

library.add(faUserSecret, faGithub, faBars)

export default {
    name: 'Nav_bar',
    data(){
        return{
            bool: false
        }
    },
    emits: ["updateParentData"],
    methods: {
        setShow(){
            this.bool = this.bool ? false : true;
            this.$emit('updateParentData', this.bool);
            console.log(this.bool)
        }
    }
}
</script>


<style scoped>
.navigation_bar {
    background: linear-gradient(-90deg, #02203c, #001528);
    width: 100vw;
    height: 50px;
    display: flex;
    position: fixed;
    z-index: 1;
}
.nav_options_container {
    flex: 1;
    height: 50px;
    display: flex;
    text-align: left;
    align-content: center;
    align-items: center;
}
.nav_options_container_right {
    flex: 1;
    height: 50px;
    display: flex;
    text-align: right;
    padding-right: 10px;
    align-content: center;
    align-items: center;
}
.nav_option_items{
    flex: 1;
    height: 30px;
    align-items: center;
    font-size: 1.5rem;
    display: flex;
    margin-left: 5px;
    font-weight: bold;
    color: white;
    font-family: 'Ubuntu', sans-serif;
}
.nav_bar_img{
    height: 20px;
    width: 20px;
    object-fit: contain;
    z-index: 0;
    transform: rotateY(180deg);
}
.font-awesome_container{
    flex: 1;
    display: grid;
    justify-content: right;
}
.font-awesome_nav_bar{
    width: 35px;
    height: 35px;
    color: white;
    transition: all 0.5s ease-out;
}
.font-awesome_nav_bar:hover{
    color: rgba(44,12,175,1);
}
/* Icon 1 */

.hamburguer{
  width: 50px;
  height: 30px;
  position: relative;
  margin: 10px auto;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .5s ease-in-out;
  -moz-transition: .5s ease-in-out;
  -o-transition: .5s ease-in-out;
  transition: .5s ease-in-out;
  cursor: pointer;
}

.hamburguer span {
  display: block;
  position: absolute;
  height: 8px;
  width: 80%;
  background: white;
  border-radius: 9px;
  opacity: 1;
  left: 0;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .25s ease-in-out;
  -moz-transition: .25s ease-in-out;
  -o-transition: .25s ease-in-out;
  transition: .25s ease-in-out;
    box-shadow: 1px 1px 2px 1px #000000;
}
.hamburguer:hover *{
    background: rgba(44,12,175,1);
}

.hamburguer span:nth-child(1) {
  top: 0px;
}

.hamburguer span:nth-child(2) {
  top: 9px;
}

.hamburguer span:nth-child(3) {
  top: 18px;
}

.open span:nth-child(1) {
  top: 8px;
  -webkit-transform: rotate(135deg);
  -moz-transform: rotate(135deg);
  -o-transform: rotate(135deg);
  transform: rotate(135deg);
}

.open span:nth-child(2) {
  opacity: 0;
  left: -60px;
}

.open span:nth-child(3) {
  top: 17px;
  -webkit-transform: rotate(-135deg);
  -moz-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  transform: rotate(-135deg);
}

</style>
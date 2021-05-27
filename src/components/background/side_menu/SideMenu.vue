<template>
    <div class="side_menu_container" v-bind:class="{'side_menu_container_active': showSideMenu}">
        <div>
            <font-awesome-icon :icon="['fas', 'id-card-alt']" class= "font-awesome_nav_bar" />
            Contact
        </div>
        <div>
            <font-awesome-icon :icon="['fas', 'info-circle']" class= "font-awesome_nav_bar" />
            About
        </div>
        <div>
            <font-awesome-icon :icon="['fas', 'sign-in-alt']" class= "font-awesome_nav_bar" />
            Login
        </div>
        <div>
            <font-awesome-icon :icon="['fas', 'sign-in-alt']" class= "font-awesome_nav_bar" />
            Help
        </div>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faIdCardAlt, faInfoCircle, faSignInAlt, faQuestionCircle } from '@fortawesome/free-solid-svg-icons'
// import {faAddressCard} from '@fortawesome/free-brands-svg-icons'

library.add(faIdCardAlt, faInfoCircle, faSignInAlt, faQuestionCircle)

export default {
    name: 'SideMenu',
    props: {
    showSideMenu: Boolean
    },
}
</script>

<style scoped>
.side_menu_container{
    position: fixed;
    width: 500px;
    height: 100vh;
    font-size: 2rem;
    left: 100%;
    font-family: 'VT323', monospace;
    background: rgb(20, 100, 121);
    transition: all 0.5s ease-out;
    display: grid;
    color: white;
    box-shadow: 3px 4px 15px 3px #000000;
    grid-template-rows: 25% 25% 25% 25%;
    justify-content: center;
    align-items: center;
}
.side_menu_container_active{
    position: fixed;
    font-family: 'VT323', monospace;
    width: 25%;
    height: 100vh;
    left: 75%;
    background: rgb(20, 100, 121);
}
.side_menu_container_active>div{
    cursor: pointer;
    transition: all 0.25s ease-out;
}
.side_menu_container_active>div:hover{
    color: rgb(25, 25, 92);
}
.font-awesome_nav_bar{
    width: 35px;
    height: 35px;
    color: black;
    transition: all 0.5s ease-out;
}

@media only screen and (max-width: 890px) {
    .side_menu_container_active{
        width: 100%;
        left: 0%;
        z-index: 1;
    }
}
</style>

<template>
    <div class="side_menu_container" v-bind:class="{'side_menu_container_active': showSideMenu}" @click="checkValue"></div>
</template>

<script>
export default {
    name: 'SideMenu',
    props: {
    showSideMenu: Boolean
    },
    methods: {
        checkValue(){
            console.log(this.showSideMenu);
        }
    }
}
</script>

<style scoped>
.side_menu_container{
    position: absolute;
    width: 500px;
    height: 100vh;
    left: 100%;
    background: rgb(31, 179, 216);
    transition: all 0.5s ease-out;
}
.side_menu_container_active{
    position: absolute;
    width: 25%;
    height: 100vh;
    left: 75%;
    background: rgb(31, 179, 216);
    transition: all 0.5s ease-out;
}
</style>

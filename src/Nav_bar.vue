<template>
    <div class="navigation_bar">
        <div class="nav_options_container">
            <div class="nav_option_items">
                {{"SmartRouter"}}
                <img class= "nav_bar_img" src="diamond.png" alt="Smart router logo" />
            </div>
        </div>
        <div class="nav_options_container">

        </div>
    </div>
</template>


<script>
export default {
  name: 'Nav_bar'
}
</script>


<style scoped>
.navigation_bar {
    background: linear-gradient(-90deg, #02203c, #001528);
    width: 100vw;
    height: 50px;
    display: flex;
}
.nav_options_container {
    flex: 1;
    height: 50px;
    display: flex;
    text-align: left;
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
</style>
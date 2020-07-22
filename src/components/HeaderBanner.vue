<template>
<div class="contianer">
    <div id="header" class="main">

        <h1>Luke <br /> Melvin.</h1>
        <img v-if="showBurger" v-on:click="showMenu()" class="menu-icon" :src="require(`@/assets/icons/menu_icon.png`)" />
        
    </div>
    <pop-out-banner />
    <div class="info-banner">
        <h4>This webiste is still under contruction. Please drop us an <a href="mailto:hello@lukemelvin.com?subject=Your%website%is%broken.%I%need%more%info!">eMail</a> if you have any questions or can't find what you need.</h4>
    </div>
</div>
</template>

<script>
    export default {
        name: 'header-banner',
        data: function () {
            return {
                showBurger: false
            }
        },
        mounted(){
            window.onload = function() {
                setTimeout(() => {scrollFunction()}, 2000);
                };
                function scrollFunction() {
                    if (onload) {
                        document.getElementById("header").style.fontSize = "100%";
                        document.getElementById("header").style.height= "10vh";
                    } else {
                        document.getElementById("header").style.fontSize = "10vh";
                        document.getElementById("header").style.height= "100vh";
                    }  

                }
        },
        methods: {
            showMenu() {
                        document.getElementById("nav-content").style.display = "inline-block";
            }
        }
    }
</script>

<style lang="css" scoped>
#header {
    background-color: #FABC2A;
    font-size: 10vh;
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    transition: 2s;
    max-width: 100vw;
    z-index: 1000;
    box-shadow: 0em 0.1em 1em rgba(0, 0, 0, .4);
    display: flex;
    align-items: center;
    justify-content: space-between;
}
h1 {
    font-family: futura;
    margin: 0;
    font-weight: bold;
    line-height: 100%;
    color: #404040;
    padding-left: 2%;
}
.info-banner {
    box-shadow: 0em 0.1em 1em rgba(0, 0, 0, .4);
    background-color: red;
    color: whitesmoke;
    display: flex;
    justify-content: center;
    max-height: 5vh;
    padding: 0.5em;
}
h4 {
    padding: 0%;
    margin: 0%;
}
img {
    height: 5vh;
    padding-right: 1%;
}
#nav-content {
    display: none;
}
</style>
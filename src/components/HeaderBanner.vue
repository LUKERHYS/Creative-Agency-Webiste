<template>
    <div id="header" class="main">
        <h1>Luke <br /> Melvin.</h1>
        <!-- <img id="scroll-icon" src="@/assets/icons/scroll.png" alt="scroll"> -->
    </div>
</template>

<script>
    export default {
        name: 'header-banner',
        mounted(){
            window.onscroll = function() {scrollFunction()};
                function scrollFunction() {
                    if (document.body.scrollTop >= 10 || document.documentElement.scrollTop >= 10) {
                        document.getElementById("header").style.fontSize = "100%";
                        document.getElementById("header").style.height= "10vh";    
                    } else {
                        document.getElementById("header").style.fontSize = "90px";
                        document.getElementById("header").style.height= "100vh";
                    }
                }
                // function scroll_arrow_delay() {
                //     setTimeout(() => {
                //         document.getElementById("scroll-icons").style.visibility = "hidden";
                //     },500);
                    
                // }
            }
        }
</script>

<style lang="css" scoped>
#header {
    background-color: #FABC2A;
    position: sticky;
    top: 0;
    transition: 0.9s;
    width: 100%;
    z-index: 1000;
}
h1 {
    margin: 0;
    padding: 2% 10%;
    line-height: 100%;
    color: #404040;
}
#scroll-icons {
    height: 10%;
}

</style>
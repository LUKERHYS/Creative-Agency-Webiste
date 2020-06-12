<template>
    <div id="header" class="main">
        <h1>Luke <br /> Melvin.</h1>
    </div>
</template>

<script>
    export default {
        name: 'header-banner',
        data: function () {
            return {
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
                        document.getElementById("header").style.fontSize = "90px";
                        document.getElementById("header").style.height= "100vh";
                    }
                }
        }
    }
</script>

<style lang="css" scoped>
#header {
    background-color: #FABC2A;
    font-size: 90px;
    height: 100vh;
    position: sticky;
    top: 0;
    transition: 0.9s;
    width: 100%;
    z-index: 1000;
}
h1 {
    margin: 0;
    padding: 20px 4%;
    line-height: 100%;
    color: #404040;
}
#scroll-icons {
    height: 10%;
}

</style>
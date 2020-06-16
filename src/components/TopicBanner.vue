<template>
        <div :key="id" v-on:click="[hidden = !hidden, handleClick]" :style="[this.divStyle, this.icon_heading_flip]" class="main">
            <div class="img-container">
                <img :src="require(`@/assets/icons/${this.imgName}`)" :alt="this.title">
            </div>
            <div class="text-container">
                <h1 :style="this.h1Style">{{title}}</h1>
            </div>
        </div>
</template>

<script>
    export default {
        name: 'topic-banner',
        data() {
            return {
                hidden: true
            }
        },
        methods: {
            handleClick() {
                eventBus.$emit('topic-selected', this.topic);
                }
        },
        props: {
            id: Number,
            bgColour: {
                type: String,
                default: "#404040"
                }, 
            titleColour: {
                type: String,
                default: "#FABC2A"
                }, 
            title: String, 
            imgName: String,
            flip: Boolean,
            blurb: String
            },
        computed: {
            divStyle() {
                return {"backgroundColor": this.bgColour};
            },
            h1Style() {
                return {"color": this.titleColour};
            },
            icon_heading_flip() {
                if(this.flip == true) {
                  return {"flex-direction": "row-reverse"};  
                }
            }
        },
        watch:{
            hidden: function (value, oldValue) { 
            const info = document.getElementById("info");
                if(this.hidden){
                    info.style.display = "none";
                } else {
                    info.style.display = null;
                }
            }
        }
    }
</script>

<style lang="css" scoped>
.main {
    display: inline-flex;
    align-items: center;
    flex-wrap: wrap;
    width: 100vw;
    max-height: 20%;
    transition-duration: 0.5s;
}
.main:hover {
    opacity: 0.8;
}
.img-container, .text-container {
    display: flex;
    align-items: center;
    justify-content: center;
    min-width: 50%;
    margin: 0;
    padding: 0;
}
h1 {
    font-size: 12vh;
}
img {
    max-height: 200px;
    max-width: 200px;
}
/* .info {
    transition-duration: 5s;
    transition:cubic-bezier(0.075, 0.82, 0.165, 1);
} */

</style>
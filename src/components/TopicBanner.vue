<template>
    <div :style="[this.divStyle, this.icon_heading_flip]" class="main">
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
        props: {
            key: Number,
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
            flip: Boolean
            },
        data: function() {
            return {

            }
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
                  return {"flex-direction": "row-reverse", };  
                }
            }
        },
        methods: {
            
        },
        mounted() {

        }
    }
</script>

<style lang="css" scoped>
.main {
    display: inline-flex;
    align-items: center;
    width: 100vw;
    height: 33%;
}
/* .main:hover {
    height: 75vh; 
} */
.img-container, .text-container {
    display: flex;
    align-items: center;
    justify-content: center;
    /* border: red solid; */
    height: 100%;
    width: 50%;
    margin: 0;
}

/* .img-container {
    justify-content: center;
} */


h1 {
    font-size: 12vh;
}
img {
    max-height: 200px;
    max-width: 200px;
}

</style>
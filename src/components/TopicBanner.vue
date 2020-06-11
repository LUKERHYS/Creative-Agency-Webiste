<template>
    <div :style="this.divStyle" class="main">
        <img :src="this.imgURL" :alt="this.title">
        <h1 :style="this.h1Style">{{title}}</h1>
        <!-- :src="this.imgBaseUrl + this.imgName" -->
    </div>
</template>

<script>
    export default {
        name: 'topic-banner',
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
            imgBaseUrl: String
            },
        data: function() {
            return {
                imgURL: null
            }
        },
        computed: {
            divStyle() {
                return {"backgroundColor": this.bgColour};
            },
            h1Style(){
                return {"color": this.titleColour};
            },
            topicHoverExpand() {
                return {"height:hover": "100vh"};
            },
            getImgUrl(base, name) {
                return require(base + name)
                }
        },
        mounted(){
            getImgUrl(this.imgBaseUrl + this.imgName)
        }
    }
</script>

<style lang="css" scoped>
.main {
    display: inline-flex;
    justify-content: space-between;
    align-items: center;
    width: 100vw;
}
/* .main:hover {
    height: 75vh; 
} */
h1 {
    padding-right: 1em;
    font-size: 12vh;
}
img {
    padding-left: 9em;
    height: 25%;
    width: 25%;
}

</style>
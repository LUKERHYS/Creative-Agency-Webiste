<template>
    <div :style="this.divStyle" class="main">
        <img :src="this.imgTitle" :alt="this.title">
        <h1 :style="this.h1Style">{{title}}</h1>
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
            imgTitle: String
            },
        data: function() {
            return {
                imgUrl: null
            }
        },
        computed: {
            divStyle () {
                return {"backgroundColor": this.bgColour};
            },
            h1Style (){
                return {"color": this.titleColour};
            }
            // ,
            // imgUrlCreation () {
            //     return this.imgUrl = "../assets/icons/" + this.imgTitle;
            // }
        }
        // ,
        // mounted() {
        //     imgUrlCreation()
        // }
    }
</script>

<style lang="css" scoped>
.main {
    display: flex;
    justify-content: space-between;
    align-content: center;
}
h1 {
    padding: 2% 15%;
    font-size: 12vh;
}
img {
    height: auto;
    width: auto;
}

</style>
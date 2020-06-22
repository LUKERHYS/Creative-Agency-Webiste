<template>
    <a :href="project.link" class="main">
        <div class="image">
            <img :src="require(`@/assets/projects/${project.image}`)" :alt="project.title" target="_blank">
            <!-- <iframe v-if="project.link" :src="project.link" frameborder="0"></iframe> -->
        </div>
        <div class="text">
            <h3>
                {{project.title}}
            </h3>
            <p>
                {{project.blurb}}
            </p>
        </div>
    </a>
</template>

<script>
    export default {
        name: 'folio-item',
        props: ['project']
        // computed: {
        //     imgfetch() {
        //         promise.fetch(require(`@/assets/projects/${project.image}`))
        //         .then(res => {
        //             if(res == null){
        //                 return "@/assets/projects/icon-img-placeholder.svg"
        //             } else {
        //                 return res
        //             }
        //         })
        //     }
        // }
    }
</script>

<style lang="css" scoped>
    div {
        /* border: solid red 1px; */
    }
    .main {
        margin: 1px;
        padding:inherit;
        overflow: wrap;
        text-decoration: none;
    }
     .text {
        background-color: #ffffff;
        padding: 0.5em;
        margin: 0;
        overflow: hidden;
    }
    .image {
        border: solid #ffffff 2px;
        overflow: hidden;
        margin: 0;
        overflow: hidden;
    }
    img {
        max-width:100%;
        height: auto;
        margin: 0;
    }
    a {
        color: #000000;
        display: flex;
        flex-direction: column;
    }
    h1:hover {
        text-decoration: underline;
    }
</style>
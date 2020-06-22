<template>
    <a :href="project.link" class="main">
        <div class="image" >
            <img :href="project.link" :src="require(`@/assets/projects/${project.image}`)" :alt="project.title" target="_blank">
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
        
    }
    .main {
        margin: 1em;
        padding:inherit;
        overflow: hidden;
        text-decoration: none;
    }
     .text {
        padding: 0.5em;
        margin: 0;
        padding: 0;
        overflow: hidden;
     }
    .image {
        display: block;
        overflow: scroll;
        max-height: 250px;
    }
    img {
        width: 100%;
        padding: 0;
    }
    a {
        color: #000000;
        display: flex;
        flex-direction: column;
    }
    h1:hover {
        text-decoration: underline;
    }
    p {
        display: none;
    }
    p:hover {
        display: inline-block;
    }
</style>
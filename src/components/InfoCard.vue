<template>
    <div id="info">

            <div v-if="this.topic" class="text-container">
                <h1 :style="this.h1Style">{{this.topic.title}}</h1>
                <p>{{this.topic.blurb}}</p>
            </div>

        </div>
</template>

<script>
    export default {
        name: 'info-card',
        props: ['topic']
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
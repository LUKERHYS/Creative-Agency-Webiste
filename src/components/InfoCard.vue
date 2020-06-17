<template>
    <div v-on:click="hidden = !hidden" id="info">

            <div v-if="topic" class="text-container">
                <h1 :style="this.h1Style">{{title}}</h1>
                <p>{{blurb}}</p>
            </div>

        </div>
</template>

<script>
    export default {
        name: 'info-card',
        props: ['topic']
    }
</script>

<style lang="scss" scoped>

</style>
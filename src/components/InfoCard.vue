<template>
    <div v-on:click="hidden = !hidden" class="info" style="display: none" id="info">

            <div class="text-container">
                <h1 :style="this.h1Style">{{title}}</h1>
                <p>{{blurb}}</p>
            </div>

        </div>
</template>

<script>
    export default {
        name: 'info-card',
        props: ['topics']
    }
</script>

<style lang="scss" scoped>

</style>
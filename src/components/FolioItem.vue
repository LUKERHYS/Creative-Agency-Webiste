<template>
    <div :v-for="(folio, index) in portfolio" :key="index" class="main">

    </div>
</template>

<script>
    export default {
        name: 'folio-item'
    }
</script>

<style lang="css" scoped>
    .main {
        height: 200px;
        width: 250px;
        background-color: dodgerblue;
        margin: 1px;
    }
</style>
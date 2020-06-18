<template>
        <div class="details-container">
            <div class="details-child">
                <h1>{{this.details.title}}</h1>
                <p>{{this.details.blurb}}</p>
            </div>
        </div>
</template>

<script>
    export default {
        name: 'info-card',
        props: ['details']
    }
</script>

<style lang="css" scoped>
.details-container {
    background-color: lightgray;
    width:100vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
}
.details-child {
    width: 50vw;
    text-justify: left;
}
</style>
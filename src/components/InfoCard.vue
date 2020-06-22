<template>
        <div class="details-container">
            <div class="details-child">
                <!-- <h1>{{this.details.title}}</h1> -->
                <h4>{{this.details.blurb}}</h4>
            </div>

            <folio-grid :portfolio="details" />

        </div>
</template>

<script>
import FolioGrid from './FolioGrid.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'info-card',
        props: ['details'],
        components: {
            'folio-grid': FolioGrid,
        }
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
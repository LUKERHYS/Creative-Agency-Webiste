<template>
        <div class="details-container">
             <div class="details-child">
                    <folio-grid :portfolio="details" />
            </div>
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
    background-color: rgba(0, 0, 0, 0.5);
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 0;
    margin-bottom: 20px;
}
.blurb {
    width: 50%;
    padding: 1em;
    overflow: scroll;
}
.examples {
    width: 50%;
    overflow: scroll;
}
.details-child {
    border-radius: 0.4em;
    display: flex;
    max-height: 80vh;
    justify-content: center;
    width: 75vw;
    background-color: rgba(255, 255, 255, 1);
    text-justify: left;
    box-shadow: 0em 0.5em 1em rgba(0, 0, 0, .4);
}
</style>
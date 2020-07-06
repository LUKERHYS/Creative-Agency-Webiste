<template>
        <div class="details-container">
             <div class="details-child">
                 <div class="blurb">
                    <h1>{{this.details.title}}</h1>
                    <h4>{{this.details.blurb}}</h4>
                 </div>
                <div class="examples">
                    <folio-grid :portfolio="details" />
                </div>
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
div {
    /* border: red solid; */
}
.details-container {
    background-color: rgba(245,245,245, 0.0);
    width: 100vw;
    max-height: 80vh;
    display: flex;
    flex-direction: column;
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
    background-color: white;
    text-justify: left;
    box-shadow: 0em 0.5em 1em rgba(0, 0, 0, .4);
}
</style>
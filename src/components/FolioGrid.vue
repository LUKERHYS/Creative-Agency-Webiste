<template>
    <div class="grid-wrapper">
        <folio-item v-for="(project, index) in this.projects" :key="index" :project="project" />
    </div>
</template>

<script>
import FolioItem from './FolioItem.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'folio-grid',
        props: ['portfolio'],
        components: {
            'folio-item': FolioItem,
        },
        data() {
            return {
                projects: []
            }
        },
        mounted() {
            this.portfolio.portfolio.forEach(project => {
                this.projects.push(project);
            });
        }
    }
</script>

<style lang="css" scoped>
    .grid-wrapper {
        width: 75%;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-auto-rows: min-content;
        padding: 0 0 2em 0;
    }
    /* .grid-wrapper {
        width: 75%;
        display: flex;
        padding: 0 0 2em 0;
    } */
</style>
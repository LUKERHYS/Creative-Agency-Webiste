<template>
    <div class="grid-wrapper">
        <folio-item />
        <folio-item />
        <folio-item />
        <folio-item />
        <folio-item />
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
        }
    }
</script>

<style lang="css" scoped>
    .grid-wrapper {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        padding: 0 0 2em 0;
    }
</style>
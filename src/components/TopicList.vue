<template>
    <ul>
        <topic-banner v-for="(topic, index) in topics" :topic="topic" :key="index" />
    </ul>
</template>

<script>
import TopicBanner from './TopicBanner.vue'
    export default {
        name: 'topic-list',
        props: ['topics'],
        components: {
            "topic-banner": TopicBanner
        }
        
    }
</script>

<style lang="css" scoped>
ul, li{
    margin: 0px;
    padding: 0px;
}
</style>
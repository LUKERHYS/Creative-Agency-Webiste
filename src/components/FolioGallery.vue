<template>
    <div>
        <folio-item 
            :v-for="item in items"
            v-bind:key="topic.id" 
            v-bind:title="item.title" 
            v-bind:client="item.client" 
            v-bind:blurb="item.blurb"
            v-bind:imgName="item.imgName"
        />
    </div>
</template>

<script>
    export default {
        name: "folio-gallery",
        data: function() {
    return {
      items: [
        {id: 1, title: "Dev.", client: "GC4C", blurb: "This is a piece for blah blah blah!", imgName: "terminals.png"},
      ]
    }
  }
    }
</script>

<style lang="scss" scoped>

</style>
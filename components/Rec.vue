<template>
    <div style="display: flex">
        <v-btn class="rec-btn" v-for="(item,idx) in items"
               :key="idx">
            {{item.title}}
        </v-btn>
    </div>
</template>

<script>
  export default {
    name: 'Rec',
    props: {
      items: Array
    }
  }
</script>

<style lang="scss">
    .rec-btn {

    }
</style>

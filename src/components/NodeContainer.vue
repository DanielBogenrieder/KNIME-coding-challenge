<template>
    <div>
      <node-card
      v-for="node in nodes"
      v-bind:key="node.id"
      v-bind:node="node"> 
      </node-card>
    </div>

</template>

<script>
import NodeCard from './NodeCard.vue';

export default {
  name: "NodeContainer",
  components: {
    NodeCard, 
  },
  props: { // to get the nodes array from 'App'
    nodes: {
      type: Array,
      required: true, 
    }
  }
};
</script>

<style scoped>

</style>
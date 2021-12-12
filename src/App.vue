<template>
  <div id="app">
    <input type="search" v-model="node" list="nodes" placeholder="Add new node..." @keyup.enter="addNode(node)">
    <datalist id="nodes">
      <!-- <option :v-for="node in nodes">{{node.name}}</option> -->
      <option value="Data Generator"></option>
      <option value="CASE Switch Data (Start)"></option>
      <option value="Cluster Assigner"></option>
    </datalist>
    <node-container :nodes="nodes"/>
  </div>
</template>

<script>
import NodeContainer from "./components/NodeContainer.vue";

export default {
  name: "App",
  components: {
    NodeContainer,
  },
  methods: {
    addNode: function(node) {
      this.nodes.push({
        id: this.idCounter++,
        name: node.name,
        text: node.text,
      });
      console.log(this.nodes);
    },

  },
  
  data() {
    return {
      idCounter: 2,
      mainProps: { width: 130, height: 120},

      nodes: [
        {
          id: 0,
          name: "Data Generator",
          text: "Source",
        },
        {
          id: 1,
          name: "CASE Switch Data (Start)",
          text: "Manipulator",
        },
        {
          id: 2,
          name: "Cluster Assigner",
          text: "Predictor",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 20px;
  margin-left: 20px;
}
</style>

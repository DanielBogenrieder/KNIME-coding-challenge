<template>
  <div class="card-group">
    <b-card-group deck class="card-group">
      <b-card  border-variant="light" :header="getName(node.name)" class="text-center" :footer="getFooter(node.text)" bg-variant="warning">
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
export default {
  name: "NodeCard",
  methods: {
    getImgUrl(imagePath) {
      return ("../assets/" + imagePath);
    },
    getName(name) {
      return name;
    },
    getFooter(footer) {
      return footer;
    }
  },
  props: { 
    node: {
      type: Object,
      required: true,
    },
  }
};
</script>

<style scoped>
  .card-group {
    display: inline-block;
    margin: 10px;
  }
</style>
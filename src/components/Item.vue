<template>
  <b-col md="3">
    <b-card :img-src="image" img-top>
      <b-card-body>
        <b-card-title>{{ name }}</b-card-title>
        <b-card-text>${{ price|dollars }}</b-card-text>
      </b-card-body>
      <div class="text-right">
        <b-button variant="primary" size="sm">Add to cart</b-button>
      </div>
    </b-card>
  </b-col>
</template>

<script>
export default {
  name: "Item",
  props: ["name", "price", "image", "invId"],
  filters: {
    dollars: num => `$${num / 100}`
  }
};
</script>
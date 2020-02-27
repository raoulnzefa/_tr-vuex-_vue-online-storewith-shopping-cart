<template>
  <b-button variant="primary" size="sm">Cart ({{ inCart.length }})</b-button>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: "ShoppingCart",
  computed: {
    ...mapGetters(['inCart'])
  },
};
</script>
<template>
  <b-container id="app" fluid>
    <h1 class="my-3">My online store</h1>

    <b-container>
      <b-row>
        <item
          v-for="item in forSale"
          :key="item.invId"
          :invId="item.invId"
          :name="item.name"
          :price="item.price"
          :image="item.image"
        />
      </b-row>
      {{ inCart }}
    </b-container>
  </b-container>
</template>

<script>
import Item from "@/components/Item";
import { mapGetters } from "vuex";

export default {
  name: "app",
  data() {
    return {};
  },
  components: { Item },
  computed: {
    // forSale() { return this.$store.getters.forSale; }
    ...mapGetters(["forSale", "inCart"])
  },
};
</script>

<style>
</style>

<template>
  <b-container id="app" fluid>
    <b-row class="my-3 align-items-center">
      <b-col md="9">
        <h1>My online store</h1>
      </b-col>
      <b-col md="3" class="text-center">
        <shopping-cart />
      </b-col>
    </b-row>

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
    </b-container>
  </b-container>
</template>

<script>
import Item from "@/components/Item";
import ShoppingCart from '@/components/ShoppingCart'
import { mapGetters } from "vuex";

export default {
  name: "app",
  data() {
    return {};
  },
  components: { Item, ShoppingCart },
  computed: {
    // forSale() { return this.$store.getters.forSale; }
    ...mapGetters(["forSale"])
  }
};
</script>

<style>
</style>

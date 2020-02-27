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
    </b-container>
  </b-container>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "app",
  data() {
    return {
      forSale: [
        { invId: 1, name: "An Item", image: "//placehold.it/200", price: 999 },
        { invId: 2, name: "Thing", image: "//placehold.it/200", price: 1499 },
        { invId: 3, name: "Doo-dad", image: "//placehold.it/200", price: 499 },
        {
          invId: 4,
          name: "Other thing",
          image: "//placehold.it/200",
          price: 299
        }
      ]
    };
  },
  components: { Item, }
};
</script>

<style>
</style>

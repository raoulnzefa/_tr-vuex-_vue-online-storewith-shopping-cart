<template>
  <b-container id="app" fluid>
    <h1 class="my-3">My online store</h1>

    <b-container>
      <b-row>
        <b-col md="3" v-for="(item, i) in forSale" :key="i">
          <b-card :img-src="item.image" img-top>
            <b-card-title>{{ item.name }}</b-card-title>
            <b-card-text>${{ item.price/100 }}</b-card-text>
            <div class="text-right">
              <b-button variant="primary" size="sm">Add to card</b-button>
            </div>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </b-container>
</template>

<script>
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
  }
};
</script>

<style>
</style>

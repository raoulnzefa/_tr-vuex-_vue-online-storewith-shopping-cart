<template>
  <div>
    <b-button variant="primary" size="sm" @click="isShowModal=true">Cart ({{ inCart.length }})</b-button>
    <b-modal v-model="isShowModal" id="shoppingCart" title="Shopping cart">
      <b-container>
        <b-row>Shopping cart items will go here.</b-row>
        <b-row class="mt-3">
          <b-table striped hover :items="cart" :fields="fields">
            <template v-slot:cell(price)="data">${{ data.item.price }}</template>
          </b-table>
        </b-row>
      </b-container>
      <template v-slot:modal-footer>
        <b-button variant="secondary" size="sm" @click="isShowModal=false">Keep</b-button>
        <b-button variant="primary" size="sm">Check out</b-button>
      </template>
    </b-modal>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "ShoppingCart",
  data() {
    return {
      isShowModal: false,
      fields: [
        {
          key: "name",
          sortable: true
        },
        {
          key: "price",
          sortable: true
        }
      ]
    };
  },
  computed: {
    ...mapGetters(["inCart", "forSale"]),
    cart() {
      // inCart内の要素がforSaleリストの要素のinvIdと合致するリストを返す
      return this.inCart.map(cartItem => {
        return this.forSale.find(forSaleItem => {
          return cartItem === forSaleItem.invId;
        });
      });
    }
  }
};
</script>
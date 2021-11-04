<template>
  <div>
    <div v-show="isEmpty">
      <p>This cart is empty</p>
    </div>
    <div class="cart">
      <CartList :products="products"/>
    </div>
  </div>
</template>

<script>
import CartList from "../components/CartList.vue"

export default {
  name: "Cart",
  components: {
    CartList,
  },
  data () {
    return {
    }
  },
  computed: {
    products() {
      return this.$root.$data.cart;
    },
    isEmpty() {
      if (this.$root.$data.cart.length > 0) return false;
      else return true;
    },
  },
};
</script>

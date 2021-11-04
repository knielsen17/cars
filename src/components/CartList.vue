<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
      </div>
      <div class="image">
        <router-link :to="'/product/' + product.id">
          <img :src="'/images/products/' + product.image">
        </router-link>
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <h2>{{product.engine}}</h2>
        <button class=auto v-on:click="removeCart(product)">Remove From Cart</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CartList',
  props: {
    products: Array
  },
  methods: {
    removeCart(product) {
      this.$root.$data.cart.splice(this.$root.$data.cart.indexOf(product), 1);
    },
  },
}
</script>

<template>
  <div>
    <h1>{{product.name}}</h1>
    <p>The price is {{product.price}}</p>
    <p>The engine is: {{product.engine}}</p>
    <div class= "productImage">
      <img :src="'/images/products/' + product.image">
    </div>
    <p>This is where I could place a long description for each car if I was to spend forever collecting the mock data.</p>
    <button class="auto" v-on:click="addToCart(product)">Add to Cart</button>
  </div>
</template>

<script>
export default {
  name: "Product",
  data() {
    return {
      product: {},
    }
  },
  created() {
    this.product = this.$root.$data.products.find(product => product.id === parseInt(this.$route.params.id));
  },
  methods: {
    addToCart(product) {
      this.$root.$data.cart.push(product);
    },
  },
}
</script>

<style>
.productImage img {
  height: 400px;
  width: 700px;
}

button {
  margin: 10px 0px 50px 0px;
}
</style>

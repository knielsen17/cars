<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.country}}</p>
      </div>
      <div class="image">
        <router-link :to="'/product/' + product.id">
          <img :src="'/images/products/' + product.image">
        </router-link>
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <router-link :to="'/product/' + product.id">
          <button class="auto">View Vehicle</button>
        </router-link>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  methods: {
  },
}
</script>

<style>
.product img {
  border: 2px solid #333;
  height: 250px;
  width: 350px;
  object-fit: cover;
}
.product {
  margin: 50px;
}
</style>

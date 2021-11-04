<template>
  <div>
    <div class="wrapper">
      <div class="search">
        <form class="pure-form">
          <i class="fas fa-search"></i><input v-model="searchText"/>
        </form>
      </div>
    </div>
    <ProductList :products="products"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ProductList from "../components/ProductList.vue";

export default {
  name: "Home",
  components: {
    ProductList,
  },
  data() {
    return {
      searchText: "",
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    },
  },
};
</script>

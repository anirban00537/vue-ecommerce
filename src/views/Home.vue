<template>
  <div class="container">
    <div class="coverImage"></div>
    <h1 class="productTitle">All Products</h1>
    <div
      class="cstmHomeContainer"
      v-if="products"
    >
      <Card
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Card from "../components/Card.vue";
export default {
  name: "Home",
  components: {
    Card
  },
  data() {
    return {
      products: []
    };
  },
  methods: {
    async fetchAllProducts() {
      const { data } = await axios.get("http://localhost:5000/api");
      console.log(data);
      this.products = data;
    }
  },
  created() {
    this.fetchAllProducts();
  }
};
</script>

<style scoped>
.cstmHomeContainer {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}
.productTitle {
  margin: 0px;
  margin-top: 20px;
}
</style>>



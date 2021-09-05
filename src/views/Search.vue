<template>
  <div class="container cstmSearch">
    <div class="input-group mb-3">
      <input
        type="text"
        class="form-control"
        placeholder="Enter keyword"
        aria-label="Enter keyword"
        aria-describedby="button-addon2"
        v-model="query"
        @keypress.enter="searchProduct"
      >
    </div>
    <div
      class="searchBody"
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
  name: "Search",
  components: {
    Card
  },
  data() {
    return {
      query: "",
      products: []
    };
  },
  methods: {
    async searchProduct() {
      const { data } = await axios.get(
        `http://localhost:5000/api/search/${this.query}`
      );
      console.log(data, "search data");
      this.products = data;
    }
  }
};
</script>

<style scoped>
.cstmSearch {
  margin-top: 20px;
}
.searchBody {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}
</style>
<template>
  <div class="container detailsContainer">
    <div class="productimage">
      <img
        :src=product.imageUrl
        class="img-fluid"
        alt="..."
      >

    </div>
    <div class="productdetails">
      <h2>
        {{product.title}}
      </h2>
      <h4 class="price">Price: {{product.price}}</h4>
      <p>{{product.description}}</p>
      <button
        type="button"
        class="btn btn-dark"
      >Add to cart</button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Details",
  data() {
    return {
      id: this.$route.params.id,
      product: {}
    };
  },
  methods: {
    async getProduct() {
      const { data } = await axios.get(
        "http://localhost:5000/api/find/one/" + this.id
      );
      console.log(data[0], "myproduct");
      this.product = data[0];
    }
  },
  created() {
    this.getProduct();
  }
};
</script>

<style scoped>
.detailsContainer {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin-top: 40px;
}
.productdetails {
  margin-left: 20px;
}
.price {
  color: rgb(55, 188, 237);
}
</style>
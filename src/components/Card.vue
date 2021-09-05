<template>
  <div class="cardProduct">
    <img
      :src=product.imageUrl
      class="cvr-img "
      alt="..."
    >
    <div class="infoSection">
      <h5>{{product.title}}</h5>
      <h3 class="price">Price: 400</h3>
      <p class="max-lines">{{product.description}}

      </p>
    </div>
  </div>
</template>
<script>
export default {
  name: "Card",
  props: {
    product: Object
  }
};
</script>
<style scoped>
.cardProduct {
  height: 280px;
  width: 240px;
  margin: 10px;
  margin-top: 40px;
  box-shadow: 12px 8px 18px 0px rgb(225 225 225);
  border-radius: 10px;
}
.imageProduct {
}
.infoSection {
  margin: 10px;
}
.max-lines {
  display: block;
  text-overflow: ellipsis;
  word-wrap: break-word;
  overflow: hidden;
  max-height: 1.6em;
  line-height: 1.8em;
  font-size: 12px;
  margin: 0px;
}
.price {
  color: rgb(55, 188, 237);
  font-size: 17px;
  margin: 0px;
}
.cvr-img {
  max-height: 160px;
  width: 100%;
}
</style>
<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-cstm ">
      <div class="container-fluid">
        <router-link
          to="/"
          class="navbar-brand"
        >Vue-commerce</router-link>
        <div class="d-inline-flex p-2">
          <router-link
            to="/search"
            class="navbar-brand"
          >
            <div class="search-container">
              <i class="fas fa-search cstmFont"></i>
              <p class="cstmFonttext">search</p>
            </div>
          </router-link>
          <div class="cartSection">
            <i class="fas fa-cart-plus"></i>
          </div>
        </div>
      </div>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped>
.navbar-cstm {
  background-color: #fcfffe;
  box-shadow: 3px 4px 13px 9px rgb(235, 235, 235);
}
.nav-link {
  color: black !important;
}
.navbar-brand {
  color: #4fc08d;
  font-weight: 700;
}

.cartSection {
  height: 40px;
  width: 40px;
  margin-top: 3px;
  margin-left: 20px;
  background-color: #4fc08d;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
}
.fa-cart-plus {
  color: white;
}
.search-container {
  width: 300px;
  display: flex;
  align-items: center;
  background-color: rgb(237, 237, 237);
  border-radius: 10px;
  padding-left: 20px;
}
.search-container > p {
  margin: 0px;
  margin-left: 10px;
  margin-bottom: 2px;
}
.cstmFonttext {
  color: black;
  font-weight: 200;
}
</style>

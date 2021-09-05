<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-cstm ">
      <div class="container-fluid">
        <router-link
          to="/"
          class="navbar-brand"
        >Vue-commerce</router-link>
        <div class="d-inline-flex p-2">
          <form class="d-flex">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            >
            <button
              class="btn btn-outline-success"
              type="submit"
            >Search</button>
          </form>
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

<style>
.navbar-cstm {
  background-color: #fcfffe;
  box-shadow: 3px 4px 13px 9px rgb(235, 235, 235);
}
.nav-link {
  color: black !important;
}
.navbar-brand {
  color: black;
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
</style>

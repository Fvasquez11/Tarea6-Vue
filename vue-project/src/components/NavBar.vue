<script>
import { RouterLink } from "vue-router";
</script>
 
<template>
  <div id="body">
    <div class="navBar">
      <div class="tittle">
        <h1>AutoBuscador</h1>
        <div id="logo">
          <b-img
            src="https://cdn-icons.flaticon.com/png/512/2953/premium/2953892.png?token=exp=1655601040~hmac=604ed3f1e1eeaefa2c8884771c6ee1d3"
            fluid-grow
          ></b-img>
        </div>
      </div>

      <div class="buttons">
        <div><b-button href="/" variant="primary">Home</b-button></div>
        <div>
          <b-button href="/search" variant="secondary">Search</b-button>
        </div>
        <div><b-button href="/about" variant="info">About</b-button></div>
      </div>
    </div>

    <div class="content">
      <RouterView></RouterView>
    </div>
  </div>
</template>

<style>
#logo {
    width: 100px;
}
.navBar {
  background-color: cyan;
  overflow: hidden;
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  padding-left: 5%;
  padding-right: 10%;
  align-items: center;
  width: 100%;
  height: 100px;
  gap: 10px;
  padding-right: 50px;
}

.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 15px;
}

.content {
  flex-flow: wrap;
}

.tittle {
  color: darkolivegreen;
  display: flex;
  align-items: center;
  gap: 20px;
}
</style>
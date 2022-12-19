<template>
  <div id="app">
    <div id="title">
      <span id="title2">BODEGUITA FLORES EIRL</span>
    </div>
    <h1>Realizar Compra</h1>
    <div id="info">
      <span>Nombre:</span>
      <input type="text" name="" id="" placeholder="Ingresa nombre cliente" />
    </div>
    <div id="info">
      <span>Correo: </span>
      <input type="text" name="" id="" placeholder="Ingresa tu correo" />
    </div>
    <ShopVue></ShopVue>
  </div>
</template>

<script>
import ShopVue from "./components/Shop.vue";

export default {
  name: "App",
  components: {
    ShopVue,
  },
};
</script>

<style lang="scss">
* {
  background-color: beige;
}
#app {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}
#title {
  background-color: black;
  height: 30px;
}
#title2 {
  background-color: black;
  color: white;
  position: absolute;
  margin-top: 5px;
  margin-left: 10px;
}
h1 {
  text-align: center;
}
#info {
  margin-top: 5px;
  text-align: center;
}
span {
  margin-right: 15px;
}
input {
  height: 25px;
  width: 400px;
}
</style>

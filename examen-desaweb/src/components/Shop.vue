<template>
  <div>
    <table align="center">
      <tbody>
        <tr>
          <td>Imagen</td>
          <td>Nombre</td>
          <td>Precio</td>
          <td>Cantidad</td>
          <td>Sub Total</td>
          <td>Eliminar</td>
        </tr>
        <tr v-for="(producto, index) in productos" :key="index">
          <td><img :src="producto.link" /></td>
          <td>{{ producto.nombre }}</td>
          <td>{{ producto.precio }}</td>
          <td><input type="text" name="" id="" v-model="cantidad" /></td>
          <td>{{ calcularSubTotal(producto.precio) }}</td>
          <td><button @click="eliminarProducto(index)">X</button></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>SUB TOTAL:</td>
          <td>{{ subTotal }}</td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>IGV:</td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>TOTAL:</td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
    <div>
      <input type="text" v-model="nuevoProducto" />
      <button @click="addTarea">añadir tarea</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ShopVue",
  props: {
    pro: Array,
  },
  data() {
    return {
      cantidad: 1,
      subTotal: 0,
      productos: [
        {
          link: "https://cdn.shopify.com/s/files/1/0604/8373/1606/products/IMG-104966_1445x.jpg?v=1658325800",
          nombre: "Apple",
          precio: 4000,
        },
      ],
    };
  },
  methods: {
    addProduct() {},
    eliminarProducto(index) {
      // console.log("ELIMINAR TAREA: ", index + 1);
      this.productos.splice(index, 1);
      // splice() El método splice() cambia el contenido de un array
      // eliminando elementos existentes y/o agregando nuevos elementos.
    },
    calcularSubTotal(index) {
      this.subTotal = this.cantidad * index;
      return this.cantidad * index;
    },
  },
};
</script>

<style scoped>
table {
  margin-top: 10px;
}
tr > td > img {
  width: 60px;
}
td {
  border-top: 1px solid gray;
}
button {
  border-radius: 50px;
  border: none;
  background-color: pink;
}
button:hover {
  background-color: yellow;
  cursor: pointer;
}
</style>

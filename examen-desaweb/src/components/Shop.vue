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
          <td>$ {{ producto.precio }}</td>
          <td><input type="text" name="" id="" v-model="cantidad[index]" /></td>
          <td>$ {{ calcularSubTotal(index) }}{{ subProducto[index] }}</td>
          <td><button @click="eliminarProducto(index)">X</button></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>SUB TOTAL:</td>
          <td>$ {{ calcularSubTotal1() }}{{ subTotal }}</td>
        </tr>

        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>IVA:</td>
          <td>$ {{ calcularIva() }}{{ iva }}</td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>TOTAL:</td>
          <td>$ {{ calcularTotal() }}{{ total }}</td>
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
  </div>
</template>

<script>
export default {
  name: "ShopVue",
  data() {
    return {
      cantidad: ["", "", ""],
      subTotal: 0,
      iva: 0,
      total: 0,
      subProducto: [0, 0, 0],
      productos: [
        {
          link: "https://cdn.shopify.com/s/files/1/0604/8373/1606/products/IMG-104966_1445x.jpg?v=1658325800",
          nombre: "Apple",
          precio: 4000,
        },
        {
          link: "https://acortar.link/fLZbUf",
          nombre: "Lenovo",
          precio: 4000,
        },
        {
          link: "https://www.hp.com/gb-en/shop/Html/Merch/Images/c07964576_1750x1285.jpg",
          nombre: "HP",
          precio: 4000,
        },
      ],
    };
  },
  methods: {
    calcularSubTotal(index) {
      if (this.cantidad[index] != "") {
        this.subProducto[index] =
          parseInt(this.cantidad[index]) * this.productos[index].precio;
      } else {
        this.subProducto[index] = 0;
      }
    },
    calcularIva() {
      this.iva = this.subTotal * 0.19;
    },
    calcularSubTotal1() {
      let sumar = 0;
      for (var i = 0; i < this.subProducto.length; i++) {
        sumar = sumar + this.subProducto[i];
      }
      this.subTotal = sumar;
    },
    calcularTotal() {
      this.total = this.subTotal + this.iva;
    },
    eliminarProducto(index) {
      return this.productos.splice(index, 1);
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

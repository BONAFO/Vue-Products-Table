<template>
  <div id="content">
    <h1>PRODUCTS</h1>
    <br />
    <div id="table-cont">
      <table>
        <thead>
          <tr>
            <td></td>
            <td>Product</td>
            <td>Price</td>
            <td>Stock</td>
          </tr>
        </thead>
        <tbody>
          <tr :class="`prod-tr ${(p.stock <= 0) ? ('prod-out-tr') : ('')}`" :key="`product-${p.id}`" v-for="p in products">
            <td><img :src="p.url" /></td>
            <td>{{ p.name }}</td>
            <td>${{ p.price }}</td>
            <td>{{ p.stock }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style>


h1{
  font-size: 6vh;
}

tr{
  transition: background-color .4s;

}

td {
  width: 40vw;
  font-size: 2.5vh;
}


.prod-tr:hover {
  color: #000000;
  cursor: pointer;
  background-color: #d2ffca;

}

.prod-out-tr:hover {
  color: #000000;
  cursor: not-allowed;
  background-color: #ff9c9c;
}



#table-cont {
  width: 80vw;
  display: inline-table;
}

img {
  width: 100px;
}

#content{
  text-align: center;
  margin-left: -20%;
}


</style>

<script setup>
let counter = 0;

class Product {
  constructor(name, price, stock, url) {
    this.id = counter;
    this.name = name;
    this.price = price;
    this.stock = stock;
    this.url = url;
  }
}

const products = [];

products.push(
  new Product(
    "SSD 240 GB",
    300,
    10,
    "https://www.venex.com.ar/products_images/1585751936_ssd_480gb_kingston_a400_2.jpg"
  )
);
counter++;

products.push(
  new Product(
    "SSD 480 GB",
    430,
    0,
    "https://www.venex.com.ar/products_images/1585751936_ssd_480gb_kingston_a400_2.jpg"
  )
);
counter++;

products.push(
  new Product(
    "SSD 1 TB",
    650,
    10,
    "https://www.venex.com.ar/products_images/1585751936_ssd_480gb_kingston_a400_2.jpg"
  )
);
counter++;

products.push(
  new Product(
    "8 GB RAM DDR4",
    320,
    18,
    "https://www.venex.com.ar/products_images/1650303429_1627495976_1626977867_1.jpg"
  )
);
counter++;

products.push(
  new Product(
    "16 GB RAM DDR4",
    600,
    3,
    "https://www.venex.com.ar/products_images/1650303429_1627495976_1626977867_1.jpg"
  )
);
counter++;

products.push(
  new Product(
    "32 GB RAM DDR4",
    1000,
    0,
    "https://www.venex.com.ar/products_images/1650303429_1627495976_1626977867_1.jpg"
  )
);
counter++;
</script>

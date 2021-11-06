<template>
<div id = "hello">
<div class="wrapper">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  <div class="products">
  <div class="container py-5">
  <div class="row text-center text-white mb-5">
      <div class="col-lg-7 mx-auto">
          <h1 class="display-4">Product List</h1>
      </div>
  </div>
  <div class="row">
  <div class="product" v-for="product in products" :key="product.id">
      <div class="col-lg-8 mx-auto">
          <!-- List group-->
          <ul class="list-group shadow">

              <!-- list group item-->
              <li class="list-group-item">
                  <!-- Custom content-->
                  <div class="media align-items-lg-center flex-column flex-lg-row p-3">
                      <div class="media-body order-2 order-lg-1">
                          <h5 class="mt-0 font-weight-bold mb-2">{{product.name}}</h5>
                          <p class="font-italic text-muted mb-0 small">The categroy for this product is given so to help the grouping of all of these products and to help you know what you need to get. <br>The category for this book is: {{product.category}}</p>
                          <div class="d-flex align-items-center justify-content-between mt-1">
                              <h6 class="font-weight-bold my-2">{{product.price}}</h6>
                              <div class="grid-item"><button v-on:click="addToCart(product)">Add to Cart</button></div>
                          </div>
                      </div><img :src="'/images/products/'+product.image" alt="Generic placeholder image" width="200" class="ml-lg-5 order-1 order-lg-2">
                  </div> <!-- End -->
              </li> <!-- End -->

          </ul> <!-- End -->
      </div>
      </div>
  </div>
</div>


  </div>
</div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  methods: {
    addToCart(product){
      this.$root.$data.cart.push(product);
    }
  }
}
</script>

<style scoped>
.wrapper {

  display: flex;
  align-items: center;
  justify-content: center;
}

#hello {
}
.row {

}
.container py-5{
width: 6px;
}
.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;

}

.testing {

}
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto auto;
  background-color: #396fba;
  padding: 10px;

}
.grid-item {
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 20px;
  font-size: 30px;
  text-align: center;
}

.product {
  margin: 10px;
  margin-top: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #F2921D;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
  justify-content: space-around;
}

button {
  height: 50px;
  background: #396fba;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>

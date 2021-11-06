<template>
<div class="wrapper">
<div class="container d-flex justify-content-center mt-50 mb-50">
    <div class="row">
        <div class="col-md-10">
          <div class="product" v-for="product in products" :key="product.id">
            <div class="card card-body">
                <div class="media align-items-center align-items-lg-start text-center text-lg-left flex-column flex-lg-row">
                    <div class="mr-2 mb-3 mb-lg-0"> <img :src="'/images/products/'+product.image" width="150" height="150" alt=""> </div>
                    <div class="media-body">
                        <h6 class="media-title font-weight-semibold"> <a href="#" data-abc="true">{{product.name}}</a> </h6>
                        <ul class="list-inline list-inline-dotted mb-3 mb-lg-2">
                            <li class="list-inline-item"><a href="#" class="text-muted" data-abc="true">{{product.category}}</a></li>
                        </ul>
                        <p class="mb-3">The categroy for this product is given so to help the grouping of all of these products and to help you know what you need to get. </p>

                    </div>
                    <div class="mt-3 mt-lg-0 ml-lg-3 text-center">
                        <h3 class="mb-0 font-weight-semibold">{{product.price}}</h3>

                         <button v-on:click="removeFromCart(product)">Remove from Cart</button>
                    </div>
                </div>
            </div>
            <br>
          </div>
        </div>
    </div>
</div>
</div>
</template>

<script>
export default {
  name: 'Cart',
  props: {
    products: Object
  },
  methods: {
    removeFromCart(product){
      const index = this.$root.$data.cart.indexOf(product);
      this.$root.$data.cart.splice(index,1);
    }
  }
}
</script>

<style scoped>
#pri {
  text-align: center;
  text-decoration: underline;
  display: flex;
  align-items: center;
}

.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  border: 2px dotted #333;

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
  background: brown;
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
  width:100%;
}

button {
  width: 100%;
  height: 50px;
  background: #396fba;;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>

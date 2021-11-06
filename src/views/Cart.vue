<template>
<div>
  <div v-if = "!empty">
  <h1 class ="title">Your Cart</h1>
  <hr>
  <p class = "thanks">We here at Bright Books thank you for buying our products. It goes to expanding our website and helps us to feed our children. So thank you so much!</p>
  <CartList :products="products" />
  </div>
  <div v-else>
    <h1 class ="title2">Your cart is currently empty!</h1>
    <hr id = "new">


  </div>
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Cart',
  components: {
    CartList
  },
  data() {
    return {
      country: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.cart;
    },
    empty(){
      return this.$root.$data.cart.length === 0;
    }
  },
  methods: {
    select(country) {
      this.country = country;
    }
  }
}
</script>

<style>
.title {
color:#396fba;
text-align: center;
text-decoration: underline;
}
.thanks{
  text-align: center;
  font-size: 25px;
  margin-bottom: 50px;
  margin-left: 10%;
  margin-right: 10%;
}
.title2 {
color:#396fba;
text-align: center;
text-decoration: underline;
}
#new {
margin-bottom: 300px;
}
</style>

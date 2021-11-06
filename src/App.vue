<template>
<div id="app">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Bright Books</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">
        <router-link to="/">
          Home
        </router-link>
        <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">
        <router-link to="/browse">
            Browse
        </router-link>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">
        <router-link to="/cart">
          <div class="menu-item cart">
            <p>{{trying}} item(s)</p>
          </div>
        </router-link>
        </a>
      </li>
    </ul>
  </div>
</nav>
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src = "https://images.unsplash.com/photo-1509021436665-8f07dbf5bf1d?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1974&q=80">
      </router-link>
    </div>
  </div>
  <router-view />
  <br>
  <br>
  <!-- Footer -->
<footer class="page-footer font-small blue">

  <!-- Copyright -->
  <div class="footer-copyright text-center py-3">Link to my Github:
    <a href="https://mdbootstrap.com/"> MDBootstrap.com</a>
  </div>
  <!-- Copyright -->

</footer>
<!-- Footer -->
</div>

</template>

<script>
export default {
  name: 'App',
  data: function () {
    return {
      number: 0
    };
  },
  computed: {
    trying: function() {
     return this.$root.$data.cart.length;
    }
  }
}
</script>

<style>
#footer {
   bottom:0;
   width:100%;
   height:60px;   /* Height of the footer */
   display: flex;
   justify-content: center;

}
* {

  box-sizing: border-box;
}

#brand {
 margin-top: 20px;
}

#app {
 background-color: #edebe9;
}
body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>

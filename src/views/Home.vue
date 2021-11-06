<template>
<div class = "testing2">
  <h1>A store to feed your Soul</h1>
  <h2>What is this store?</h2>
  <ul>
    <li class = "first">First of all it isn't a real one it is for a class project</li>
    <li class = "second">It's a place where you can find the best book to learn more about Christ</li>
    <li class = "third">It's a place to learn</li>
  </ul>
  <br>
  <h2>Why should you use this store?</h2>
  <ul>
    <li>The materials can be sorted for easy studying</li>
    <li>Our prices are cheaper</li>
    <li>It goes to helping my family eat a nice Sunday dinner</li>
  </ul>
  <br>
  <p>Overall this store will help us to learn more about the New Testament and Christ. We have been told many times to find the best books to study and this store will help you to do just that.</p>
  <div id = "breaker"><br></div>
  <p id = "quote">Your mind is precious! It is sacred. Therefore, the education of one’s mind is also sacred. Indeed, education is a religious responsibility. Of course, our opportunities and abilities will vary a great deal. But, in the pursuit of one’s education, individual desire is more important than is the institution you choose; personal drive is more significant than is the faculty.</p>
  <p class = "author">President Russel M. Nelson</p>
</div>
</template>

<script>

export default {
  name: 'Home',
  components: {

  },
  data() {
    return {
	searchText: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
}
</script>
<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

#breaker {
  background-color: #396fba;
}

.testing2 {
margin-left:10%;
margin-right:10%;
}

.author {
font-size: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

h1 {
  color: #d4af37;
  display: flex;
  justify-content: center;
}
h2 {
  background-color: #396fba;
  font-size: 25px;
  color: white;
}

p {
  font-size: 20px;
}
ul {
  font-size: 20px
}
#quote {
  font-style: italic;
  font-size: 20px;
  margin-left: 5%;
  margin-right: 5%;

}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>

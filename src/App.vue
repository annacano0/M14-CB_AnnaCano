<script setup>
import {ref, reactive} from 'vue'
//define a reactive variable
const num=ref(0) 

//define a reactive variable when array or object (non-simple objects)
const user=reactive({name:'pepe', age: 22})

const increment=()=>{
  num.value++
}

const addYears=()=>{
  user.age++
}

const title="Hello world"
const imgUrl='https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Jan_Vermeer_-_The_Art_of_Painting_-_Google_Art_Project.jpg/800px-Jan_Vermeer_-_The_Art_of_Painting_-_Google_Art_Project.jpg'

//initialize reactive variable
const carName=ref('')

//show products with v-for
const products=[
  {
    id:1,
    name: 'television',
    price: 1234.5,
  },
  {
    id:2,
    name: 'pants',
    price: 25.99,
  },
  {
    id:1,
    name: 'posticle',
    price: 2.5,
  }
]

//v-show
const show=ref(true)


</script>

<template>
  <h1>VUE</h1>
  <div class="example">
    <h3>Counter:{{ num }}</h3>
    <button @click="increment">+</button>
  </div>

  <div class="example">
    <h3>User</h3>
    <p>Name: {{ user.name }}</p>
    <p>Years: {{ user.age }}</p>
    <button @click="addYears">Add years</button>
  </div>

  <div class="example">
    <h2 v-bind:title="title">Hover mouse</h2>
    <img :src="imgUrl" alt="Img">
  </div>

  <div class="example">
    <h3>Car name: {{ carName }}</h3>
    <input type="text" v-model="carName" placeholder="Citroen">
  </div>

  <div class="example">
    <h3>Products:</h3>
    <ul class="product">
      <li v-for="product in products" :key="product.id">
        <p>Name: {{ product.name }}</p>
        <p>Price: {{ product.price }}€</p>
      </li>
    </ul>
  </div>

  <div class="example">
    <h3 v-if="loged">Welcome User</h3>
    <h3 v-else>Please log in</h3>
  </div>

  <div class="example">
    <button @click="show = !show">Toggle visibility</button>
    <p v-show="show">I'm seen</p>
  </div>
</template>

<style scoped>

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.example{
  border: 1px solid rgba(255, 255, 255, 0.445);
  border-radius: 1em;
  margin: 2em;
  padding: 2em;
}

img{
  max-width: 20em;
}
h3{
  font-weight: bold;
}
</style>

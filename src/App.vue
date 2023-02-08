<template>
  <a :href="url">My GitHub</a> <!-- aslinya v-bind -->
  <img :alt="alt" :src="src">
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h2>{{ welcome_message }} {{ name }}</h2>
  <button @:click="changeName">Change Name</button> <!-- @ aslinya v-on-->
  
  <!-- Dua Arah & Realtime-->
  <input type="text" v-model="text">
  {{ text }}
  
  <!-- Menampilkan list menggunakan perulangan dan if-else-->
  <div v-if="products.length">
    <ul>
      <li v-for="item in products" :key="item.id">
       {{ item.title }} - {{ item.price }}
      </li>
    </ul>  
  </div>

  <div v-else>
    <p> No Data Found </p>
  </div>

  <div v-if="users.length">
    <ul>
      <li v-for="user in users" :key="user.id">
       {{ user.title }} - {{ user.price }}
      </li>
    </ul>  
  </div>

  <div v-else>
    <p> No Data Found </p>
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import { onBeforeMount } from 'vue';

export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      welcome_message: "Welcome",
      name: "Adrian Hadinata",
      url: "https://github.com/ozmoza234",
      alt: "Vue logo",
      src: require("./assets/logo.png"),
      text: "",
      products:[
        {
          id: 1, title: "Product 1", price:3000
        },
        {
          id: 2, title: "Product 2", price:3000
        },
        {
          id: 3, title: "Product 3", price:3000
        },
        {
          id: 4, title: "Product 4", price:3000
        },
      ],
      users:[]
    }
  },
  methods:{
    changeName(){
      this.name = "Joko"
    }
  },
  //Life Cycle Hooks (Historycal)
  beforeCreate(){
    console.log('Before Created');
  },
  created(){
    console.log('Created');
  },
  beforeMount(){
    console.log('Before Mount');
  },
  mounted(){
    console.log('Mounted');
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

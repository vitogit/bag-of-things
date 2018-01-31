<template>
  <div id="app">
    <bag/>
  </div>
</template>

<script>
import bag from './Bag.vue'

// const STORAGE_KEY = 'bag_of_many_things'
// const itemStorage = {
//   fetch() {
//     const todos = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]');
//     todos.forEach((todo, index) => {
//       todo.id = index
//     })
//     itemStorage.uid = todos.length
//     return todos
//   },
//   save(todos) {
//     localStorage.setItem(STORAGE_KEY, JSON.stringify(todos))
//   }
// };

export default {
  name: 'app',
  components: {bag},  
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

<template>
  <div id="app">
    <div class="container">
      <header class="has-text-centered">
        <h1 class="title">
          Bolsas con cosas
        </h1>
        <p class="subtitle">
          Agrega, remueve y saca cosas de bolsas virtuales.
        </p>
      </header>
      <div class="has-text-left">
        <a class="button is-primary is-large" @click="addBag">+</a>
        <a class="button is-info is-large" @click="save">Grabar</a>
      </div>
      <br>
      <div>

        <bag 
          class ="bag" 
          @onRemove="removeBag(bag.number)"
          :name="bag.name"
          :items="bag.items" 
          v-for="(bag, index) in bags" 
          :key="index"/>
      </div>
    </div>
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
      bags: [{name:'bag 1', items:[], number: 1}],
      number: 1
    }
  },
  methods: {
    addBag() {
      this.number++
      this.bags.push({name:'bag '+this.number, number: this.number})
    },
    removeBag(number) {
      this.bags = this.bags.filter(e => e.number !== number);
    },
    save(){
      
    }
  }
}
</script>

<style>
  .bag {
    margin: 20px;
    width: 45%;
    display: inline-block;
  }
</style>

<template>
  <div>
    <h1>{{ title }}</h1>
    <form @submit="calculate">
      <textarea type="" @input="handelInput"/>
      <button type="submit">Calculate</button>
    </form>
    <ul v-if="list">
      <li v-for="item in list" :key="item.name">
        {{item.key}}: {{item.value}}
      </li>
    </ul>
  </div>
</template>

<style>
  ul{
    list-style: none;
    }

    div{
      background: #fff;
    }

    div{
      color: black
    }

</style>
// lllllll
<script>
// import Vue from '
import Vue from "vuetify"
import Component from 'vue-class-component'

export default @Component({
})

class App extends Vue {
  title = "The best"
  string = ''
  list = []
  constructor(){
    super()
  }
  handelInput(e) {
    this.string = e.target.value
  }

  calculate(e){
    e.preventDefault()
    const arr = this.string.split('').map(item => item === item.toUpperCase() && item !== ' ' && item !== ','?`,${item}`: item).join('').split(",").map(item => item.trim().toLowerCase())
    console.log(arr);
    const uniqArr = arr.map(item => item.trim().toLowerCase()).filter((item, index, arr) => arr.indexOf(item) === index)
    const obj = {}
    console.log(uniqArr);
    const answer = uniqArr.map(item => {
      const count = arr.filter(i => item === i).length
      // console.log(this.list.push({key: item, value: count}))
      return {key: item, value: count}
      
    })
    
    console.log(this.list = answer);
  }
  }
</script>

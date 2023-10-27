<template>
  <div>
    <input type="text" v-model="newTodoItem">
    <button v-on:click="addTodo">추가</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodo() {
      console.log(this.newTodoItem);
      axios.get("http://localhost:8981/ins?str="+this.newTodoItem)
        .then(res=>{
          console.log(res.data);
        })
        .catch(res=>{
          console.log(this.response.data)
        })
    }
  }
}
</script>



<style scoped>

</style>

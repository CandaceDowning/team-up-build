<template>
  <div>
    <form @submit = "addTodo">
      <input type = "text" name = "title" placeholder="Add todo" v-model = "title"/>
      <input type = "submit"  valuse = "Submit" class = "btn"/>

    </form>
  </div>
</template>


<script>
  import axios from 'axios'
  export default{
    name: 'AddTodo',
    data(){
      return{
        title: ''
      }
    },
    methods: {
      addToDo(e){
        e.preventDefault();
        const newTodo = {
          // id: uuid.v4(),
          title: this.title,
          completed: false
        }
        this.$emit('add-todo', newTodo)
        this.title = ''
      }
    }
  }
</script>

<style scoped>
  form{
    display: flex;
  }

  input[type="text"]{
    flex: 10;
    padding: 5px;
  }
</style>

<template>
  <div id="container">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import "./assets/css/reset.css";
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import TodoFooter from "./components/TodoFooter.vue";

export default {
  name:"app",
  data(){
return {
  id:0,
  todos:[
    // {id:0, text:"할일1", modify:false, update:true },
    // {id:1, text:"할일2", modify:true, update:true},
    // {id:2, text:"할일3", modify:false, update:true},  
]
}
  },
  components: {
    TodoHeader: TodoHeader, // 키 속성명 : 속성값 변수의이름 <처럼 같은 이름이면 생략가능
    TodoInput,
    TodoList,
    TodoFooter,
  },
  created(){
    let id = localStorage.getItem("id")
    let todos = JSON.parse(localStorage.getItem("todos"))
    if(id){
      this.$store.stste.id = id
    }
    if(todos){
      this.$store.todos = todos
    } else {
      this.todos = []
    }
  },
  };


</script>

<!-- scoped 속성을 가지고 있으면, css 속성은 현재의 -->
<style scoped>
#container {
  max-width: 600px;
  margin: 50px auto;
  box-shadow:5px 10px 10px rgba(0, 0, 0, 0.03);
  background:#fff;
}
</style>

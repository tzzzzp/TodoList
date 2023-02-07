<template>
   
        <li>
          <label>
            <input type="checkbox" :checked="todo.done" @click="check(todo.id)"/>
            <span>{{todo.thing}}</span>
          </label>
          <button class="btn btn-danger" @click="del(todo.id)">删除</button>
        </li>
    

</template>

<script>
export default{
    name:'uselis',
    props:['todo','checktodo','deltodo'],
    methods:{
      check(id){
       this.checktodo(id)
      },
      del(id){
        if(confirm('确定删除吗')){
          console.log(id);
        this.deltodo(id)
      }
        }
      }
    }



</script>

<style scoped>
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

li:hover{
  background-color: #ddd;
}
li:hover button{
  display: block;
}
</style>
<template>
    <div class="todo-footer" v-show="todos.length">
        <label>
          <input type="checkbox" :checked="isall" @click="overall"/>
        </label>
        <span>
          <span>已完成{{overtodos}}</span> / 全部{{todos.length}}
        </span>
        <button class="btn btn-danger" @click="delall">清除已完成任务</button>
      </div>

</template>

<script>


export default{
    name:'useverb',
    props:['todos','alltodos','delovertodo'], 
    computed:{
      overtodos(){
        let i = 0
        this.todos.forEach(todo => {
          if(todo.done) i++
        });
        return i
      },
      isall(){
         return this.overtodos === this.todos.length
      }
    },
    methods:{
      overall(e){
        this.alltodos(e.target.checked);
      },
      delall(){
        if(confirm('确认删除所有已完成的事件？')){
          this.delovertodo()
        }
      }

    }
   
}
</script>

<style>
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>
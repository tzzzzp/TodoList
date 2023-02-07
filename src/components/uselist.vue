<template>
    <div>
        <ul class="todo-main">
            <uselis v-for="todoObj in todos" :key="todoObj.id" :todo='todoObj'
            :checktodo="checktodo" 
            :deltodo="deltodo"
            />
      </ul>
     
       
    </div>
</template>

<script>
import uselis from './uselis.vue';
export default{
    name:'uselist',
    components:{uselis},
    data() {
        return {
  
        }
    },
    methods:{
      
    },
    props:['todos','checktodo','deltodo']
}
</script>

<style scoped>
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}

</style>
<template>
<div @click="$emit('toggle-click',task.id)" :class="[task.reminder ? 'reminder' : '','task']">
     <h3>{{task.text}} <i @click="DeleteTask(task.id)" class="fas fa-times"></i></h3>
     <p>{{task.day}}</p>
</div>
 
</template>

<script>
export default {
props:['task'],
methods:{
  DeleteTask(id){
    this.$emit('delete-task',id)
  }
}
}
</script>

<style scope>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
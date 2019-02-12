<template>
    <div class="todos">
        <center><h2>My Tasks</h2></center>

<div class="row">
  <div class="column" style="background-color:#0000FF;">
    <h2><u>My Todo List</u></h2>
    <p><input type="checkbox">meeting<br>
       <input type="checkbox">gym<br>
       <input type="checkbox">meal prep<br>
       <input type="checkbox">homework<br>
    </p>
  </div>
  <div class="column" style="background-color:#fFAEBD7;">
    <h2><u>Due Date</u></h2>
    <p>01/31/19<br>
       02/08/19<br>
       01/30/19<br>
       04/12/19<br>

    </p>
  </div>
  <div class="row" style="background-color:#FAEBD7;">
    <button class="button" v-on:click="addToDoItem">Remove</button>

  </div>
  

</div>

        
        <div></div>

            <button class="button" v-on:click="addToDoItem">Insert</button>
        </div>
        

</template>

<script lang="ts">
import vue from 'vue';
import {Component} from "vue-property-decorator"
@Component
export default class ToDos extends vue{
    mytodos: ToDo[] = [
        { name: "Tod one", duedate: undefined},
        {name: "todo two", duedate: undefined }
        ];

addToDoItem() {
    this.mytodos.push({name: `todo${new Date().getTime()}`, duedate: undefined});
}
}
interface ToDo {
    name: string;
    duedate: Date | undefined;
}



</script>

<style scoped>
* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 33.33%;
  padding: 10px;
  height: 700px; 
}


.row:after {
  content: "";
  display: table;
  clear: both;
}
</style>



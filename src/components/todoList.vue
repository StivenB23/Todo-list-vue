<template>
        <div class="form">
            <form  @submit.prevent="createTask">
                <h1>Number of todos {{tasks.length}}</h1>
              <label class="label" for="task">New todo:</label><br/>
              <input class="input" type="text" v-model="newTask" id="task" />
              <button class="button" type="button" @click="createTask()" >Add todo</button>
            </form>
            <div class="list">
                <h1>List Todos</h1>
                <ul>
                  <li
                    class="task"
                    v-for="(task, i) in tasks"
                    :key="'task' + i"
                    :class="{completed: task.completed}"
                    @click="completeTask(task.text)"
                  >{{task.text}}</li>
                </ul>
            </div>
        </div>

  </template>
  
  <script>
  export default {
    data: () => ({
      newTask: "",
      tasks: []
    }),
    methods: {
      createTask() {
        let task = {
          text: this.newTask,
          completed: false
        };
        this.tasks.push(task);
        this.newTask = "";
        console.log(this.tasks);
      },
      completeTask(taskText) {
        for (let i = 0; i < this.tasks.length; i++) {
          let task = this.tasks[i];
          if (taskText === task.text) {
            task.completed = !task.completed;
          }
        }
      }
    }
  };
  </script>
  <style scoped>
    
    input{
        outline:none;
    }
    label{
        font-weight:bold;
        color:#2c3e50;
    }
  .form{
    display:flex;
    justify-content:space-evenly;
    padding:10px;
    margin:10px auto;
    background:#FFF;
    width:900px;
    box-shadow:0px 5px 8px rgba(235, 235, 235, 0.753);
  }
  .form input[type="text"]{
    border: none;
    width:100%;
    border-bottom:1px solid #2c3e50;
  }
  [class="button"]{
    margin-top:10px;
    border:none;
    background-color:rgb(143, 236, 179);
    padding:7px;
    font-size:17px;
    cursor:pointer;
  }
  [class="button"]:hover{
    transition: .2s ease;
    border-radius:4px;
    background-color:rgb(128, 211, 160);
  }
  .task {
    cursor: pointer;
    margin: 10px 0;
  }
  .completed {
    text-decoration: line-through;
    color: rgb(142, 216, 124);
  }
  </style>
<template>
  <div class="container" id="user-goals">
    <header>
      <h1>Vue vourse Goal</h1>
    </header>
    <h2>Current Goals</h2>
    <input type="text" v-model="add"> <button @click="addTask()">Submit</button>
    <ul>
      <li v-for="(task, index) in list" :key="task">
        <h3>{{ task }}</h3>
        <button @click="removeTask(index)" class="removeButton">Remove</button>
      </li>
    </ul>

  </div>
</template>

<script setup >

import { ref } from 'vue';
let add = "";
const list = ref(["task1", "task2", "task3"]);

function addTask() {
  list.value.push(add);
}
function removeTask(index) {
  list.value.splice(index, 1);
}
</script>

<style>
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: #1b995e;
  color: white;
  text-align: center;
}

#user-goals {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}

#user-goals h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #1b995e;
  margin: 0 0 1rem 0;
}

#user-goals h3 {
  margin-left: 20px;
  margin-right: 20px;
}

#user-goals ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}



#user-goals li {
  display: flex;
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background-color: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}

#user-goals input {
  font: inherit;
  border: 1px solid #ccc;
}

#user-goals input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
}

#user-goals button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#user-goals .removeButton {
  list-style: none;
  background-color: #ff3b97;
  margin-left: auto;
  border-radius: 15%;
}


#user-goals button:hover,
#user-goals button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>

<template>
  <div>

    <input type="text" v-model="add"> <button @click="addTask()">Submit</button>
    <ul>
      <li v-for="(task) in list" :key="task">
        {{ task }}
      </li>
    </ul>

  </div>
</template>

<script setup >

import { ref } from 'vue';
let add = "";
const list = ref(["test1", "test2", "test3"]);

function addTask() {
  list.value.push(add);
}
</script>

<style></style>

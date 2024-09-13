<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">user {{ name }} is active</p>
  <p v-else-if="status === 'pending'">user {{ name }} is pending</p>
  <p v-else>user {{ name }} is not active</p>

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask">
    <button type="submit">Submit</button>
  </form>


  <h3>Tasks:</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>
        {{ task }}
      </span>
      <button @click="deleteTask(index)">Delete</button>
    </li>
  </ul>
  <a :href="link">Click for Google</a>

  <br>
  <button @click="toggleStatus">Change Status</button>

</template>

<script setup>
import { ref } from 'vue';

  const name = ref("John Doe")
  const status = ref('active')
  const tasks = ref(['task-1', 'task-2', 'task-3'])
  const newTask = ref('')

  const toggleStatus = () => {
    if (status.value === 'active') {
      status.value = 'pending'
    } else if (status.value === 'pending') {
      status.value = 'inactive'
    } else {
      status.value = 'active'
    }
  };

  const addTask = () => {
    if (newTask.value.trim() !== "") {
      tasks.value.push(newTask.value);
      newTask.value = "";
    }
  };

  const deleteTask = (index) => {
    tasks.value.splice(index, 1);
  }
</script>

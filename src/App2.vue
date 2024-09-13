<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">user {{ name }} is active</p>
  <p v-else-if="status === 'pending'">user {{ name }} is pending</p>
  <p v-else>user {{ name }} is not active</p>
  <h3>Tasks:</h3>
  <ul>
    <li v-for="(task, tasks) in tasks" :key="task">{{ task }}</li>
  </ul>
  <a :href="link">Click for Google</a>

  <br>
  <button @click="toggleStatus">Change Status</button>

</template>

<script>
export default {
  data() {
    return {
      name: "John Doe",
      status: "pending",
      tasks: ['task-1', 'task-2', 'task-3'],
      link: 'https://google.com'
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending'
      } else if (this.status === 'pending') {
        this.status = 'inactive'
      } else {
        this.status = 'active'
      }
    }
  }
};
</script>

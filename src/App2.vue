<!-- <template>
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
</script> -->


<!-- Composition API -->
<!-- <template>
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
        <button @click="deleteTask(index)">x</button>
      </li>
    </ul>
    <a :href="link">Click for Google</a>
  
    <br>
    <button @click="toggleStatus">Change Status</button>
  
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue';
  
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
    };
  
    onMounted(async () => {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/todos")
        const data = await response.json();
        tasks.value = data.map((task) => task.title)
      } catch {error} {
        console.log('Error fetching tasks')
      }
    });
  </script> -->
  
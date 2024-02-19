<template>
    <div class="task-list">
      <h1>Tasks</h1>
      <ul>
        <li v-for="task in tasks" :key="task.id">{{ task.title }}</li>
      </ul>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  interface Task {
    id: number;
    title: string;
  }
  
  export default defineComponent({
    setup() {
      const tasks = ref<Task[]>([]);
  
      // Simulated tasks data
      const fetchTasks = () => {
        setTimeout(() => {
          tasks.value = [
            { id: 1, title: 'Task 1' },
            { id: 2, title: 'Task 2' },
            { id: 3, title: 'Task 3' },
          ];
        }, 1000);
      };
  
      fetchTasks();
  
      return {
        tasks,
      };
    },
  });
  </script>
  
  <style scoped>
  .task-list {
    font-family: Arial, sans-serif;
    border: 1px solid #ccc;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .task-list h1 {
    font-size: 24px;
    margin-bottom: 10px;
  }
  
  .task-list ul {
    list-style-type: none;
    padding: 0;
  }
  
  .task-list li {
    background-color: #f9f9f9;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 5px;
  }
  </style>
  
<template>
  <div :class="[task.reminder == true ? 'reminder' : '', 'task']">
    <h3>{{ task.text }} <span @click="onDelete(task.id)">❌</span></h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      
    },
  },
};
</script>

<style scoped>
div {
  background: #f5f5f5;
  padding: 0.5rem 1rem;
  margin: 0.5rem 0;
  border-radius: 0.5rem;
}
h3 {
  display: flex;
  justify-content: space-between;
}
p {
  font-size: 0.75rem;
  font-weight: 100;
}
.reminder {
  border-left: 0.25rem solid green;
}
</style>

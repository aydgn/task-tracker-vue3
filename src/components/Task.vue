<template>
  <div
    @dblclick="$emit('toggle-reminder', 'task.id')"
    :class="[task.reminder == true ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }} <span @click="$emit('delete-task', task.id)">❌</span>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

/* SCRIPT */

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

/* STYLE */

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
h3 span:hover {
  cursor: pointer;
}
p {
  font-size: 0.75rem;
  font-weight: 100;
}
.reminder {
  border-left: 0.25rem solid green;
}
</style>

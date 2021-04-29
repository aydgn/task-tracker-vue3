<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="Add Task" />
  </header>
</template>

<script>
import Button from "./Button";
export default {
  name: "Header",
  props: {
    title: String,
  },
  components: { Button },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  margin: 1rem 0;
  border-bottom: 1px solid #696969;
  border-radius: 0.5rem;
}
</style>

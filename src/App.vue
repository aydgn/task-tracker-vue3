<template>
  <Header title="Task Tracker" />
  <Tasks
    @toggle-reminder="toggleReminder"
    @delete-task="deleteTask"
    :tasks="tasks"
  />
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      if (confirm("Silmek istediğinden emin misin?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
    toggleReminder(id) {
      /* map ile task.id si emit ile gelen id den farklı olan tasklerin reminderını ters çeviriyoruz.
        Eğer id si değişmemişse taski aynı şekilde döndürüyoruz.*/
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Sözlü mülakat zamanını seç",
        day: "30 Nisan, 17:00",
        reminder: true,
      },
      {
        id: 2,
        text: "Ananas suyu iç",
        day: "30 Nisan, 12:00",
        reminder: true,
      },
      {
        id: 3,
        text: "Kargoyu kontrol et",
        day: "30 Nisan, 11:00",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
body {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  max-width: 480px;
  margin: 0 auto;
}
</style>

<template>
  <Header title="Task Tracker" />
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
  data() {
    return {
      tasks: [],
    };
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

<style></style>

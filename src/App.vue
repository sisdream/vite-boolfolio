<script>
import axios from "axios";

import ProjectCard from "./components/ProjectCard.vue";

export default {
  data() {
    return {
      title: "Vite Boolfolio!",
      projects: [],
    };
  },

  components: {
    ProjectCard,
  },
  created() {
    this.fecthProjects();
  },

  methods: {
    fecthProjects() {
      axios.get(`http://127.0.0.1:8000/api/projects`)
        .then((res) => {
          console.log('>>> response fetch projects:', res.data)
          this.projects = res.data.data;
          console.log(this.projects)
        })
        .catch((err) => console.error('>>> errore fetch projects:', err));
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <div v-if="projects.length > 0" class="row g-3">
      <project-card
        v-for="project in projects"
        :project="project"
      ></project-card>
    </div>

   

    <div v-else>Nulla da mostrare</div>
  </div>
</template>

<style lang="scss">

</style>
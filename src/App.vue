<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import ProjectsList from "./components/projects/ProjectsList.vue";
const apiBaseUrl = "http://localhost:8000/api/";
export default {
  name: "App",
  components: { AppHeader, ProjectsList },
  data: () => ({
    projects: [],
  }),
  methods: {
    fetchProjects() {
      axios.get(apiBaseUrl + "projects").then((res) => {
        this.projects = res.data;
      });
    },
  },
  created() {
    this.fetchProjects();
  },
};
</script>

<template>
  <AppHeader />
  <main class="container my-5">
    <ProjectsList :projects="projects" />
  </main>
</template>

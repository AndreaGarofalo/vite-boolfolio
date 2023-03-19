<script>
import axios from "axios";
import ProjectCard from "../components/projects/ProjectCard.vue";
const apiBaseUrl = "http://localhost:8000/api/";
export default {
  name: "ProjectDetailPage",
  components: { ProjectCard },
  data: () => ({
    project: null,
  }),
  methods: {
    getProject() {
      const endpoint = apiBaseUrl + "projects/" + this.$route.params.id;
      axios
        .get(endpoint)
        .then((res) => {
          this.project = res.data;
        })
        .catch(() => {
          this.$router.push({ name: "not-found" });
        });
    },
  },
  created() {
    this.getProject();
  },
};
</script>

<template>
  <ProjectCard :project="project" :isDetail="true" />
</template>

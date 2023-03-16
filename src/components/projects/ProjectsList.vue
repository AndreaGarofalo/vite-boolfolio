<script>
import ProjectCard from "./ProjectCard.vue";

export default {
  name: "ProjectsList",
  props: { projects: Array },
  components: { ProjectCard },
};
</script>

<template>
  <div v-if="projects.length" class="d-flex justify-content-between flex-wrap">
    <ProjectCard
      v-for="project in projects"
      :key="project.id"
      :project="project"
    />
  </div>
  <h4 v-else class="text-center">Non ci sono progetti</h4>
</template>

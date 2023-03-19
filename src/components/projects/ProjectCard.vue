<script>
export default {
  name: "ProjectsCard",
  props: { project: Object, isDetail: Boolean },
  computed: {
    projectDate() {
      const date = new Date(this.project.updated_at);
      let day = date.getDay();
      let month = date.getMonth();
      const year = date.getFullYear();
      const hours = date.getHours();
      const minutes = date.getMinutes();
      const seconds = date.getSeconds();

      if (day < 10) day = "0" + day;
      if (month < 10) month = "0" + month;

      return `${day}/${month}/${year} alle ${hours}:${minutes}:${seconds}`;
    },
  },
};
</script>

<template>
  <div class="card my-5" :class="isDetail ? `col-12` : `col-3 mx-1`">
    <div class="card-header">
      <h5 class="card-title">{{ project.title }}</h5>
    </div>
    <img
      v-if="project.screen"
      :src="project.screen"
      class="card-img-top img-fluid"
      :alt="project.slug"
    />
    <div class="card-body">
      <p class="card-text">{{ project.description }}</p>
    </div>
    <div class="card-footer d-flex justify-content-between align-items-center">
      <time>Pubblicato il: {{ projectDate }}</time>
      <RouterLink
        v-if="!isDetail"
        class="btn btn-primary"
        :to="{ name: 'project-detail', params: { id: project.id } }"
        >Vedi</RouterLink
      >
    </div>
  </div>
</template>

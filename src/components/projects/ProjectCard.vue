<script>
export default {
  name: "ProjectsCard",
  props: { project: Object },
};
</script>

<template>
  <div class="card my-5" style="width: 18rem">
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
    <div class="card-footer">
      <time>Pubblicato il: {{ project.updated_at }}</time>
    </div>
  </div>
</template>

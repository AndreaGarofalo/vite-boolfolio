<script>
export default {
  name: "NotFoundPage",
};
</script>

<template>
  <div
    class="d-flex flex-column align-items-center justify-content-center vh-100"
  >
    <h1>404 | Not Found</h1>
    <button class="btn btn-sm btn-secondary" @click="$router.back()">
      indietro
    </button>
  </div>
</template>

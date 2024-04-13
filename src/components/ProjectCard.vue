<script>
export default {
  data() {
    return {};
  },
  props: {
    project: Object,
  },
};
</script>

<template>
  <div class="col-4">
    <div class="card h-100">
      <img
        v-if="project.image"
        :src="project.image"
        class="card-img-top"
        alt="project related picture"
      />
      <div class="card-body">
        <h5 class="card-title text-capitalize">{{ project.title }}</h5>
        <p class="card-text">{{ project.description }}</p>
        <h6 class="d-inline me-2">Type:</h6>
        <span>{{ project.category}}</span>
        
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
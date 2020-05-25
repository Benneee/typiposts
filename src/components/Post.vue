<template>
  <div v-if="post">
    <div>
      <div class="title">
        <h4>{{ post.title }}</h4>
      </div>
      <div class="body">
        <p id="post">
          {{ post.body }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
  props: ['post'],
};
</script>

<style scoped>
.title {
  text-transform: capitalize;
}
#post {
  margin-bottom: 0.5rem;
}
</style>

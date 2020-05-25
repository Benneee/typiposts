<template>
  <div v-if="post">
    <div>
      <div class="title">
        <h4>{{ post.title }} &nbsp;</h4>
        <i class="fas fa-trash" @click="$emit('delete-post', post.id)"></i>
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
  methods: {},
};
</script>

<style scoped>
.title {
  text-transform: capitalize;
  display: flex;
}

.title h4 {
  align-self: flex-start;
  flex: 10;
}

.title i {
  align-self: center;
  text-align: right;
  flex: 2;
}

#post {
  margin-bottom: 0.5rem;
}

i {
  color: #fff;
  cursor: pointer;
  font-size: 1rem;
}
</style>

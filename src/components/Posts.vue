<template>
  <div class="posts">
    <article v-for="(post, index) of posts" :key="'post' + index">
      <Post :post="post" />
    </article>
  </div>
</template>

<script>
import Post from '@/components/Post.vue';
export default {
  name: 'Posts',
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  components: {
    Post,
  },
};
</script>

<style scoped>
.posts {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 100%;
  margin: 0.5rem 0;
}

article {
  border-radius: 0.3rem;
  background: rgb(71, 71, 197);
  width: 15rem;
  padding: 0.5rem 1.2rem;
  color: #fff;
  margin-bottom: 10px;
}
</style>

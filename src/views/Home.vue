<template>
  <div id="app">
    <AddPost v-on:add-post="addPost" />
    <Posts :posts="posts" v-on:delete-post="deletePost" />
  </div>
</template>

<script>
import Posts from '@/components/Posts.vue';
import AddPost from '@/components/AddPost.vue';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    Posts,
    AddPost,
  },
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    deletePost(id) {
      if (confirm('Are you sure you want to delete this post?')) {
        axios
          .delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
          .then((res) => {
            if (res) {
              this.posts = this.posts.filter((post) => post.id !== id);
            }
          })
          .catch((error) => console.log(error));
      }
    },
    addPost(newPost) {
      const { title, body } = newPost;
      axios
        .post('https://jsonplaceholder.typicode.com/posts', {
          title,
          body,
        })
        .then((res) => {
          if (res) {
            this.posts = [...this.posts, res.data];
          }
        })
        .catch((error) => console.log(error));
    },
  },
  created() {
    axios
      .get('https://jsonplaceholder.typicode.com/posts')
      .then((res) => {
        const posts = [...res.data].slice(0, 12);
        this.posts = [...posts];
      })
      .catch((error) => console.log('error: ', error));
  },
};
</script>

<style>
@import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#nav {
  padding: 10px;
  text-align: center;
}

#nav a {
  font-weight: bold;
  color: #fff;
}
body {
  margin: 0;
  padding: 0;
}

#nav a.router-link-exact-active {
  color: rgb(115, 115, 200);
  text-decoration: underline;
}
</style>

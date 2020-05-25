<template>
  <div id="app">
    <Header />
    <AddPost />
    <Posts :posts="posts" />
  </div>
</template>

<script>
import Posts from '@/components/Posts.vue';
import AddPost from '@/components/AddPost.vue';
import Header from '@/components/layout/Header.vue';

export default {
  name: 'app',
  components: {
    Posts,
    Header,
    AddPost,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title:
            'sunt aut facere repellat provident occaecati excepturi optio reprehenderit',
          body:
            'quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto',
        },
        {
          id: 2,
          title: 'qui est esse',
          body:
            'est rerum tempore vitae sequi sint nihil reprehenderit dolor beatae ea dolores nequ fugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis qui aperiam non debitis possimus qui neq nisi nulla',
        },
        {
          id: 3,
          title: 'ea molestias quasi exercitationem repellat qui ipsa sit aut',
          body:
            'et iusto sed quo iure nvoluptatem occaecati omnis eligendi aut ad nvoluptatem doloribus vel accusantium quis pariatur nmolestiae porro eius odio et labore et velit aut',
        },
        {
          id: 4,
          title: 'nesciunt quas odio',
          body:
            'repudiandae veniam quaerat sunt sed nalias aut fugiat sit autem sed est nvoluptatem omnis possimus esse voluptatibus quis nest aut tenetur dolor neque',
        },
      ],
    };
  },
};
</script>

<style>
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
  color: greenyellow;
}
</style>

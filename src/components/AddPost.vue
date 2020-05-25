<template>
  <div class="content">
    <button class="btn-show" v-if="showBtn" @click="show">Add Post</button>
    <form @submit.prevent="addPost" v-if="showForm">
      <input
        type="text"
        v-model="title"
        placeholder="Enter Title"
        class="title"
      />
      <textarea rows="15" v-model="body" cols="10"></textarea>

      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
// import { v4 as uuidv4 } from 'uuid';
export default {
  name: 'AddPost',
  data: () => {
    return {
      body: '',
      title: '',
      showForm: false,
      showBtn: true,
    };
  },
  methods: {
    addPost() {
      const newPost = {
        title: this.title,
        body: this.body,
      };
      this.showForm = false;
      this.showBtn = true;
      this.$emit('add-post', newPost);
    },
    show() {
      if (!this.showForm) {
        this.showForm = true;
        this.showBtn = false;
      }
    },
  },
};
</script>

<style scoped>
.content {
  display: flex;
  justify-content: center;
  align-content: center;
}

.title {
  margin: 0.3rem 0;
  padding: 0.4rem;
}

form {
  width: 50vw;
  margin: 0.5rem;
  display: flex;
  flex-direction: column;
}

.btn {
  color: #fff;
  border-radius: 5px;
  background: rgb(71, 71, 197);
  padding: 0.8rem;
  margin-top: 0.3rem;
  cursor: pointer;
}

.btn-show {
  color: #fff;
  border-radius: 5px;
  background: rgb(71, 71, 197);
  padding: 0.5rem;
  margin-top: 0.3rem;
  cursor: pointer;
}

.btn:hover,
.btn-show:hover {
  background: rgb(41, 41, 180);
}
</style>

<template>
  <div class="content">
    <button class="btn-show" v-if="showBtn" @click="show">Add Post</button>
    <form v-if="showForm">
      <input type="text" placeholder="Enter Title" class="title" />
      <textarea rows="15" cols="10"></textarea>

      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
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
    addPost() {},
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
}

.btn-show {
  color: #fff;
  border-radius: 5px;
  background: rgb(71, 71, 197);
  padding: 0.5rem;
  margin-top: 0.3rem;
}
</style>

<template>
  <div>
    <header class="header">
      <h1>Typiposts</h1>
      <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style scoped>
.header {
  background: rgb(41, 40, 40);
  color: #fff;
  text-align: center;
  padding: 3px;
}
</style>

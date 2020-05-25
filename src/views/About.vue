<template>
  <div class="about">
    <article>
      <h1>Note From Benneee</h1>

      <p>
        First CLI-enable Vue app. Up next, I will be building the vue version
        for my angular pokelogue application. I might throw in a weather app
        somewhere in between this and vue-pokelogue, either way, I am really
        just trying to understand the basics of Vue.js and be as good and
        comfotable in Vue.js as I am in Angular, probably sometime really soon,
        I can start writing TypeScript with Vue as well, definitely looking
        forward to that.
      </p>

      <span>
        Stay Tuned!
      </span>
    </article>
  </div>
</template>

<style scoped>
.about {
  text-align: center;
  border: 1rem solid rgb(71, 71, 197);
  height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
article {
  width: 70vw;
}

article p {
  margin-bottom: 1rem;
}

article span {
  border-bottom: 0.3rem solid rgb(71, 71, 197);
  transition: 1s;
  font-size: 1.4rem;
}

article span:hover {
  background: rgb(71, 71, 197);
  color: #fff;
  font-weight: bold;
}

@media screen and (max-width: 640px) {
  article p {
    margin-bottom: 0.5rem;
    font-size: 0.9rem;
  }

  article span {
    font-size: 1rem;
  }

  .about {
    border: 0.5rem solid rgb(71, 71, 197);
  }
}
</style>

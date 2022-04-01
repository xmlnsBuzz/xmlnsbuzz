<template>
  <article>
    <h1>{{ mountain.title }}</h1>
    <p v-if="$fetchState.pending">
      <span class="loading"></span>
    </p>
    <p v-else-if="$fetchState.error">Error while fetching mountains 🤬</p>
    <section>
      <!-- <img :src="mountain.image" :alt="mountain.title" /> -->
      <p>
        {{ mountain.description }}
        <!-- {{description}} -->
      </p>
    </section>
    <button @click="goBack">Back</button>
  </article>
</template>


<script>
export default {
  watch: {
    "$route.query": "$fetch",
  },
  data() {
    return {
      //   mountain: this.$route.params.slug,
      mountain: {},
    };
  },
  async fetch() {
    this.mountain = await this.$http.$get(
      //   `http://localhost:3000/blog.json?this.$route.params.slug`
      //   `http://localhost:3000/blog.json?${this.$route.params.slug}`
      `https://3udju.sse.codesandbox.io/blog.json`
    );
  },
  methods: {
    goBack() {
      return this.$router.go(-1);
    },
  },
};
</script>
<style scoped>
article {
  max-width: 600px;
  margin: 0 auto;
}
img {
  height: 200px;
}
p {
  text-align: left;
}
</style>

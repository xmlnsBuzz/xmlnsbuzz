<template>
  <div>
    <the-blog-all />
  </div>
</template>

<script>
import TheBlogAll from "../../components/TheBlogAll.vue";
export default {
  components: { TheBlogAll },
  data() {
    return {
      mountains: [],
    };
  },
  async fetch() {
    this.mountains = await fetch(
      "https://3udju.sse.codesandbox.io/blog.json"
    ).then((res) => res.json());
  },
};
</script>

<style>
</style>
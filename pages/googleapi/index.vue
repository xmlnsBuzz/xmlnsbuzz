<template>
  <div>
    <!-----the-blog-all /----->
    <TheGoogleApi />
    <!-- <the-google-api /> -->
  </div>
</template>

<script>
import TheGoogleApi from "../../components/TheGoogleApi.vue";
export default {
  components: { TheGoogleApi },
  data() {
    return {
      mountains: [],
    };
  },
  async fetch() {
    this.mountains = await fetch(
      "https://script.googleusercontent.com/macros/echo?user_content_key=iJLLGWy2XR3sBUCgLGyOkMvMEtQyBtDX432ju76TaihrsAWR3cGyLpJKIuY6jm6C-mqVEylQlWywuJOpMs7XlCJK27Nw5KP_m5_BxDlH2jW0nuo2oDemN9CCS2h10ox_1xSncGQajx_ryfhECjZEnEgKUSEKZAbo5b7L4PwFjGqt_woMYrb75_GzgQmLwUbGQbjOPl8Wh2pVXHVJwPC6Bbc5Yu1BFlTCGGaU2pP6Ntk&lib=MUx4MpC2NIHY9zDpjxHlJlBlfZc1fPD1m"
    ).then((res) => res.json());
  },
};
</script>

<style>
</style>
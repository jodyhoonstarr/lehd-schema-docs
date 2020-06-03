<template>
  <div class="container">
    <nuxt-content :document="page" />
    <br>
    <hr>
    <br>
    <v-btn color="primary" nuxt to="/">
      Home
    </v-btn>
  </div>
</template>

<script>
export default {
  components: {},
  asyncData({ $content, params, error }) {
    return $content(params.slug)
      .fetch()
      .then((page) => {
        return { page };
      })
      .catch((e) => {
        error({ statusCode: 404, message: "Page not found" });
      });
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 50vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: left;
}
</style>

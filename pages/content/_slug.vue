<template>
  <div class="container">
    <H1 class="surround">Content from the slug</H1>
    <nuxt-content :document="page" />
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
  text-align: center;
}

.surround {
  padding: 12px;
}
</style>

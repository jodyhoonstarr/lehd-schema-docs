<template>
    <v-container class="fill-height" fluid>
      <v-row align="center" justify="center">
        <v-col cols="12">
          <nuxt-content :document="page" />
          <br />
          <v-btn color="primary" nuxt to="/">
            Home
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
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
.nuxt-content-highlight code {
  min-width: 100% !important;
  padding-top: 1rem;
  padding-left: 2rem !important;
  font-weight: normal !important;
}
.nuxt-content-highlight pre {
  background: none !important;
}
.nuxt-content-highlight code::before{
  content: "";
}
</style>

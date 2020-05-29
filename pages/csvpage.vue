<template>
  <article>
    <h1 v-for="item in page.body">{{ item.title }} {{ item.description }}</h1>
  </article>
</template>

<script>
export default {
  name: "csvpage",
  async asyncData({ $content }) {
    const page = await $content("home").fetch();

    return {
      page,
    };
  },
};
</script>

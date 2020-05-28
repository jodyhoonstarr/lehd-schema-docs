<template>
  <v-container fluid>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="items"
          label="Standard"
        ></v-select>
      </v-col>

      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="items"
          filled
          label="Filled style"
        ></v-select>
      </v-col>

      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="items"
          label="Outlined style"
          outlined
        ></v-select>
      </v-col>

      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="items"
          label="Solo field"
          solo
        ></v-select>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
  export default {
    props:{
      items: {
        type: Array,
        required: true
      },
    },
    name: "Test",
    // data: () => ({
    //   items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    // }),
  }
</script>

<style scoped>

</style>

<template>
  <v-layout column align-center justify-center>
    <div>
      <h1>
        {{ title }}
      </h1>
      <NuxtLink to="/">
        Home page
      </NuxtLink>
    </div>
  </v-layout>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  head () {
    return { title: this.title }
  },
  data () {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  computed: {
    title () {
      return this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>

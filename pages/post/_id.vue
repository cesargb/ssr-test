<template>
  <div>{{ post.name}}</div>
</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const posts = await $axios.$get('https://api.github.com/users/cesargb/repos')
    const post = posts.filter(post => post.id === parseInt(params.id))[0]
    return { post }
  }
}
</script>

<style>

</style>

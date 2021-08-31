<template>
  <div>
    <li v-for="post in posts" :key="post.id">
      <nuxt-link :to="'post/' + post.id">{{ post.name }}</nuxt-link>

    </li>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get('https://api.github.com/users/cesargb/repos')
    return { posts }
  }
}
</script>

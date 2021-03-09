<template>
  <div>
    <p>about me</p>
    <NuxtLink to="/">Home</NuxtLink>
    <ol>
      <li><NuxtLink to="/about/child1">Child #1</NuxtLink></li>
      <li><NuxtLink to="/about/child2">Child #2</NuxtLink></li>
    </ol>
    <NuxtChild />
  </div>
</template>

<script>
export default {
  // asyncData() {
  //   // eslint-disable-next-line nuxt/no-timing-in-fetch-data
  //   return new Promise((resolve) => setTimeout(() => resolve({}), 2500))
  // },
  head: {
    title: 'about',
    meta: [
      {
        hid: 'about-description',
        name: 'description',
        content: 'This about page is all about me and only me!',
      },
    ],
  },
}
</script>

<style lang="scss" scoped></style>

<template>
  <div>
    <h1>About Dad Jokes</h1>
    <p>This is a simple Joke project by Syfon to learn Nuxtjs</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'About Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  }
}
</script>

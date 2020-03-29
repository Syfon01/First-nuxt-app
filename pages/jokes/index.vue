<template>
  <div class="container">
    <h2>Jokes all the way</h2>
  </div>
</template>
<script>
export default {
  data() {
    return {
      jokes: []
    }
  },
  created() {

  },
  head() {
    return {
      title: 'Dad Jokes page',
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

<template>
  <div>
    <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
    <h2 class="text-gray">{{ joke }}</h2>
    <hr />
    <p>Joke Id: {{ $route.params.id }}</p>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data() {
    return {
      joke: {}
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      )
      this.joke = res.data.joke
    } catch (err) {
      console.log(err)
    }
  },
  head() {
    return {
      title: ' Single Jokes page',
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

<template>
  <div class="container">
    <h2>Jokes all the way</h2>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      header: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      console.log(res.data)
    } catch (err) {
      console.log(err)
    }
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

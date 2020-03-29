<template>
  <div class="container">
    <searchJokes @search-text="searchText" />
    <joke
      v-for="joke in jokes"
      :key="joke.id"
      :id="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>
<script>
import axios from 'axios'
import Joke from '~/components/joke'
import searchJokes from '~/components/searchJoke'
export default {
  components: {
    Joke,
    searchJokes
  },
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
    } catch (err) {
      console.log(err)
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )
        this.jokes = res.data.results
      } catch (err) {
        console.log(err)
      }
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

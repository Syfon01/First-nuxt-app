<template>
  <div>
    <form @submit.prevent="onSubmit">
      <input
        type="search"
        name=""
        v-model="text"
        placeholder="search joke ...."
      />
      <input type="submit" value="searchjoke" />
    </form>
  </div>
</template>
<script>
export default {
  name: 'searchJokes',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-text', this.text)
      this.text = ''
    }
  }
}
</script>

<template>
  <div class="header">
    <nuxt-link to="/" class="brand">
      <h2 class="title">Dad Jokes App</h2>
    </nuxt-link>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/jokes">Jokes</nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>
<script>
export default {
  name: 'Navbar'
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-content: center;
  border: 1px dotted #ccc;
  margin-bottom: 1rem;
  padding: 0.2rem;
}
.title {
  color: #526488;
  font-size: 2rem;
}
ul {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 2rem;
}
ul a {
  display: inline-block;
  background: #333;
  color: #fff;
  padding: 0.5rem 1rem;
  margin-right: 0.5rem;
}
</style>

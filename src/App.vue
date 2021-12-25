<template>
  <main>
    <h1>tests</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </main>
</template>

<style lang="scss">
html, body, #app {
  margin: 0;
  padding: 0;
  max-height: 100%;
  max-width: 100%;
  height: 100%;
  width: 100%;
  overflow: hidden;
  background: $light;
}
</style>
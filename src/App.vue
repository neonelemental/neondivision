<template>
  <main>
    <nav>
      <div class="brand">
        <p class="logo">
          {{logo}}
        </p>
      </div>
      <div class="nav-items">
        <ul>
          <li>
            <router-link to="/" :class="isActive('home')? 'active' : null ">st-100</router-link>
          </li>
          <li>
            <router-link to="/about" :class="isActive('about')? 'active' : null">about</router-link>
          </li>

        </ul>
      </div>
    </nav>
    <div class="content">
      <router-view/>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      logo: "neon/"
    }
  },
  methods: {
    isActive (routeName) {
      return routeName === this.$router.currentRoute.value.name;
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Courier+Prime&display=swap');

html, body, #app {
  margin: 0;
  padding: 0;
  max-height: 100%;
  max-width: 100%;
  height: 100%;
  width: 100%;
  overflow: hidden;
  background: $blue-accent;
  color: $light;
  font-family: $primary-font;
}

a {
  color: $red;
  text-decoration: none;
}

* {
  transition: linear 150ms;
}

nav {
  padding-top: .5rem;
  height: 3rem;
  width: 100%;
  display: flex;
  color: $red;
  align-items: center;

  .brand {
    display: flex;
    align-items: center;
    padding-left: 2rem;

    .logo {
      font-size: 1.25rem;
      letter-spacing: .1rem;
      flex: 1;
      margin: 0;
      color: $light;
    }
  }

  .nav-items {
    padding-right: 2rem;
    display: flex;
    width: 100%;
    flex: 3;
    justify-content: flex-end;

    ul {
      flex: 1;
      list-style: none;
      display: flex;
      justify-content: right;

      li {
        &:not(:last-child){
          margin-right: 1rem;
        }

        a {
          &:hover {
            background: darken($red, 6%);
          }

          &.active {
            background: $red;
          }

          border-radius: 2px;
          padding: .5rem .75rem;
          color: $light;
        }
      }
    }
  }
}

main {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: stretch;

  > .content {
    flex: 32;
    align-items: stretch;
  }
}

.sidebar {
  display: flex;

  .band {
    flex: 1;
    align-items: stretch;
  }

  .band-1 {
    background: $blue-accent;
  }

  .band-2 {
    background: $red;
  }

  .band-3 {
    background: $light-accent;
  }
}

a {
  color: $light-accent;
}
</style>
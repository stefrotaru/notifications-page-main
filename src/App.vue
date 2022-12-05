<template>
  <NotificationsContainer />
</template>

<script>
import NotificationsContainer from './components/NotificationsContainer.vue'

export default {
  name: 'App',
  components: {
    NotificationsContainer,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@500;800&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  height: 100vh;
  font-family: 'Plus Jakarta Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: hsl(210, 60%, 98%);

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

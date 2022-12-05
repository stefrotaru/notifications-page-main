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

#app {
  height: 100%;
  font-family: 'Plus Jakarta Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

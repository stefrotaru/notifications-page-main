<template>
  <div class="container">
    <NotificationsHeader v-bind:notificationsNo="notificationsNo"/>
    <NotificationCard v-for="user in users" :key="user" v-bind:user="user"/>
  </div>
</template>

<script>
import NotificationsHeader from './NotificationsHeader.vue';
import NotificationCard from './NotificationCard.vue';

export default {
  name: 'NotificationsContainer',
  data() {
    return {
      notificationsNo: 3,
      users: [
        {
        "name": "Mark Webber",
        "profilePic": "avatar-mark-webber.webp",
        "interaction": "react",
        "interactionTarget": "My first tournament today!",
        },
        {
        "name": "Angela Gray",
        "profilePic": "avatar-angela-gray.webp",
        "interaction": "follow",
        "interactionTarget": "",
        },
        {
        "name": "Jacob Thompson",
        "profilePic": "avatar-jacob-thompson.webp",
        "interaction": "joined",
        "interactionTarget": "My first tournament today!",
        },
        {
        "name": "Rizky Hasanuddin",
        "profilePic": "avatar-rizky-hasanuddin.webp",
        "interaction": "message",
        "interactionTarget": "Hello, thanks for setting up the Chess Club. I've been a member for a few weeks now and I'm already having lots of fun and improving my game.",
        },
        {
        "name": "Kimberly Smith",
        "profilePic": "avatar-kimberly-smith.webp",
        "interaction": "comment",
        "interactionTarget": "image-chess.webp",
        },
        {
        "name": "Nathan Peterson",
        "profilePic": "avatar-nathan-peterson.webp",
        "interaction": "react",
        "interactionTarget": "5 end-game strategies to increase your win rate",
        },
        {
        "name": "Anna Kim",
        "profilePic": "avatar-anna-kim.webp",
        "interaction": "leave",
        "interactionTarget": "Chess Club",
        },
      ]
    }
  },

  components: {
    NotificationsHeader,
    NotificationCard,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  border: 1px solid black;
  border-radius: .5rem;
  width: 700px;
  padding: 1rem;
}
</style>

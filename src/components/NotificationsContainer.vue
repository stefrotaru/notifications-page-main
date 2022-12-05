<template>
  <div class="container">
    <NotificationsHeader v-model:isSeen="isSeen" v-model:notificationsNo="notificationsNo"/>
    <NotificationCard v-for="user in users" :key="user" v-bind:user="user" v-bind:isSeen="isSeen"/>
  </div>
</template>

<script>
import NotificationsHeader from './NotificationsHeader.vue';
import NotificationCard from './NotificationCard.vue';

export default {
  name: 'NotificationsContainer',
  data() {
    return {
      isSeen: false,
      notificationsNo: 3,
      users: [
        {
        "name": "Mark Webber",
        "profilePic": "avatar-mark-webber.webp",
        "interaction": "react",
        "interactionTarget": "My first tournament today!",
        "timeStamp": "1m ago",
        "seen": false,
        },
        {
        "name": "Angela Gray",
        "profilePic": "avatar-angela-gray.webp",
        "interaction": "follow",
        "interactionTarget": "",
        "timeStamp": "5m ago",
        "seen": false,
        },
        {
        "name": "Jacob Thompson",
        "profilePic": "avatar-jacob-thompson.webp",
        "interaction": "joined",
        "interactionTarget": "Chess Club",
        "timeStamp": "1 day ago",
        "seen": false,
        },
        {
        "name": "Rizky Hasanuddin",
        "profilePic": "avatar-rizky-hasanuddin.webp",
        "interaction": "message",
        "interactionTarget": "Hello, thanks for setting up the Chess Club. I've been a member for a few weeks now and I'm already having lots of fun and improving my game.",
        "timeStamp": "5 days ago",
        "seen": true,
        },
        {
        "name": "Kimberly Smith",
        "profilePic": "avatar-kimberly-smith.webp",
        "interaction": "comment",
        "interactionTarget": "image-chess.webp",
        "timeStamp": "1 week ago",
        "seen": true,
        },
        {
        "name": "Nathan Peterson",
        "profilePic": "avatar-nathan-peterson.webp",
        "interaction": "react",
        "interactionTarget": "5 end-game strategies to increase your win rate",
        "timeStamp": "2 weeks ago",
        "seen": true,
        },
        {
        "name": "Anna Kim",
        "profilePic": "avatar-anna-kim.webp",
        "interaction": "leave",
        "interactionTarget": "Chess Club",
        "timeStamp": "2 weeks ago",
        "seen": true,
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

<style scoped>
.container {
  background: white;
  box-shadow: 0px 0px 11px 5px rgba(0,0,0,0.10);
  border-radius: .5rem;
  width: 575px;
  padding-inline: 1.5rem;
}
</style>

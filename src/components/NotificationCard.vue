<template>
    <div>
        <div>
            <img :src="require('@/assets/images/' + user.profilePic)" alt="asd">
            <p>{{user.name}} 
                <span v-if="user.interaction == 'react'">reacted to your recent post {{user.interactionTarget}}</span>
                <span v-if="user.interaction == 'follow'">followed you</span>
                <span v-if="user.interaction == 'joined'">has joined your group {{user.interactionTarget}}</span>
                <span v-if="user.interaction == 'message'">has sent you a private message {{user.interactionTarget}}</span>
                <span v-if="user.interaction == 'comment'">commented on your picture</span>
                <span v-if="user.interaction == 'leave'">left the group {{user.interactionTarget}}</span>
            </p>
        </div>
        
        <img v-if="user.interaction == 'comment'" :src="require('@/assets/images/' + user.interactionTarget)" alt="asd">
        <div v-if="user.interaction == 'message'">
            <p>{{interactionTarget}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NotificationCard',
    props: ['user'],
    methods: {
        
    },
    beforeMount() {}
}
</script>

<style scoped>

</style>
<template>
    <div class="card" v-bind:class = "(user.seen)?'seen':'unseen'">
        <div class="card__default">
            <img class="profile_pic" :src="require('@/assets/images/' + user.profilePic)" alt="asd">
            <div class="card__text">
                <p v-bind:class = "(user.seen)?'':'unseen-bubble'">
                    <span class="user_name">{{user.name}}</span> &nbsp;  
                    <span v-if="user.interaction == 'react'">reacted to your recent post <span class="highlight-post">{{user.interactionTarget}}</span></span>
                    <span v-if="user.interaction == 'follow'">followed you</span>
                    <span v-if="user.interaction == 'joined'">has joined your group <span class="highlight-group">{{user.interactionTarget}}</span></span>
                    <span v-if="user.interaction == 'message'">has sent you a private message</span>
                    <span v-if="user.interaction == 'comment'">commented on your picture</span>
                    <span v-if="user.interaction == 'leave'">left the group <span class="highlight-group">{{user.interactionTarget}}</span></span>
                </p>
                <span class="card__timeStamp">{{user.timeStamp}}</span>
            </div>
            <img class="commented-picture" v-if="user.interaction == 'comment'" :src="require('@/assets/images/' + user.interactionTarget)" alt="asd">
        </div>
        
        
        <div class="prv_msg" v-if="user.interaction == 'message'">
            <p>{{user.interactionTarget}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NotificationCard',
    props: ['user'],
    methods: {},
    beforeMount() {}
}
</script>

<style scoped>
.card {
    color: hsl(219, 12%, 42%);
}
.card__default {
    /* border: 1px solid grey; */
    border-radius: 10px;
    overflow: hidden;
    padding-inline: .7rem;
    margin-bottom: .5rem;

    display: flex;
    /* align-items: center; */
}
.profile_pic {
    height: 2.2rem;
    padding-right: .7rem;
    position: relative;
    top: .75rem;
}
.card__text {
    font-size: .8rem;
}
.user_name {
    font-weight: 800;
    color: black;
}
.card__timeStamp {
    font-size: .6rem;
    position: relative;
    bottom: 15px;
}
.prv_msg {
    border: 1px solid hsl(205, 33%, 90%);
    border-radius: 4px;
    padding-inline: 1rem;
    margin-bottom: 1rem;
    max-width: 460px;
    margin-left: auto;
    font-size: .8rem;
}



.unseen {
    background: hsl(210, 60%, 98%);
    border-radius: 10px;
}
.unseen-bubble::after {
    content: "";
    margin-left: 7.5px;
    height: 5px;
    width: 5px;
    background: hsl(1, 90%, 64%);
    border-radius: 50%;
    display: inline-block;
    position: relative;
    bottom: 1.7px;
}

.commented-picture {
    height: 2.2rem;
    margin-left: auto;
    align-self: center;
}

.highlight-post {
    font-weight: 800;
}
.highlight-group {
    font-weight: 800;
    color: hsl(219, 85%, 26%);
}
</style>
<template>
    <div class="header">
        <div class="title-wrapper">
            <h1 class="header__title">Notifications</h1>
            <span class="header__counter">{{notificationsNo}}</span>
        </div>
        <a class="header__btn">Mark all as read</a>
    </div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'

export default ({
    name: 'NotificationsHeader',
    props: ['notificationsNo']
})
</script>

<style scoped>
.header {
    display: flex;
    align-items: center;
    /* flex-wrap: wrap; */
    justify-content: space-between;
}
.title-wrapper {
    display: flex;
    /* flex-direction: row; */
    align-items: center;
}

.header__title {
    font-size: 1.2rem;
}

.header__counter {
    margin-inline-start: .5rem;
    border: 1px solid black;

}

.header__btn {
    
}
</style>

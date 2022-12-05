<template>
    <div class="header">
        <div class="title-wrapper">
            <h1 class="header__title">Notifications</h1>
            <span v-if="(notificationsNo > 0)" class="header__counter">{{notificationsNo}}</span>
        </div>
        <a class="header__btn" @click="this.markAsSeen()">Mark all as read</a>
    </div>
</template>

<script>
export default ({
    name: 'NotificationsHeader',
    data() {
        return {
            childIsSeen: false,
            childNotificationsNo: 3,
        }
    },
    created() {
        this.childIsSeen = this.isSeen;
        this.childNotificationsNo = this.notificationsNo;
    },
    methods: {
        markAsSeen() {
            this.childIsSeen = true;
            this.childNotificationsNo = 0;
            this.$emit('update:isSeen', this.childIsSeen);
            this.$emit('update:notificationsNo', this.childNotificationsNo);
        }
    },
    props: ['notificationsNo', 'isSeen']
})
</script>

<style scoped>
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-block: 1.5rem;
}
.title-wrapper {
    display: flex;
    align-items: center;
}

.header__title {
    font-size: 1.2rem;
}

.header__counter {
    margin-inline-start: .5rem;
    padding: .1rem .5rem;
    border: none;
    border-radius: 5px;
    background-color: hsl(219, 85%, 26%);
    color: white;
}

.header__btn {
    color: hsl(219, 12%, 42%);
}
.header__btn:hover {
    color: hsl(219, 85%, 26%);
    cursor: pointer;
}
</style>

<template>
    <div class="users-list flex">
        <span  v-for="(item, index) in users.slice(0,5)" :key="index" class="user">
            <img
            :src="require('../static/users/' + item.img)"
            :alt="item.name"
            />
        </span>
        <span v-if="users.length > 5" class="user user-indicator flex">
            <span class="user-no flex">+{{users.length - 5 }}</span>
        </span>

    </div>
</template>
<script>
export default {
    name: 'UsersList',
    props: {
        users: {
            type: Array,
            default: []
        }
    }
}
</script>
<style scoped>
    .users-list {
        justify-content: flex-start;
        align-items: center;
        align-content: center;
        --gap: 0
    }
    .user {
        max-width: 26px;
        max-height: 26px;
        height: 26px;
        width: 26px;
        display: inline-block;
        border-radius: 50%;
        align-self: center;
    }
    .user img {
        width: 100%;
        height: 100%;
    }
    .user:not(:first-child) {
        transform: translateX(-30%);
    }
    .user:nth-child(3) {
        transform: translateX(-60%);
    }
    .user:nth-child(4) {
        transform: translateX(-90%);
    }
    .user:nth-child(5) {
        transform: translateX(-120%);
    }
    .user:nth-child(6) {
        transform: translateX(-150%);
    }
    .user.user-indicator {
        border: 2px solid #fff;
        background: hsla(264, 100%, 98%, 1);
        color: hsla(259, 63%, 59%, 1);
        font-size: 12px;
        align-items: center;
        justify-content: center;
        align-content: center;
        position: relative;
    }
    .user-no {
        align-items: center;
        justify-content: center;
        align-self: center;
    }
</style>
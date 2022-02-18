<template>
    <div>
        <span  v-for="(item, index) in users.slice(0,5)" :key="index" class="users">
            <img
            :src="require('../static/users/' + item.img)"
            :alt="item.name"
            />
        </span>
        <span v-if="users.length > 5" class="user user-indicator">+{{users.length - 5 }}</span>

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

</style>
<template>
    <div class="user-nav flex">
        <Button outline ><img src="~/static/icons/lightning.svg" alt="" /> Upgrade now</Button>
        <p class="icons"><img src="~/static/icons/settings.svg" /></p>
        <p class="icons"><img src="~/static/icons/bell.svg" /></p>
        <div class="user-img">
            <img src="~/static/users/user.svg" alt="" />
        </div>
    </div>
</template>
<style scoped>
    .user-nav {
        --gap: 1.5rem;
        align-items: center;
        justify-content: flex-end;
        align-content: center;
    }
    .user-nav > * {
        align-self: center;
    }
    .user-nav p {
        margin: 0;
    }
    .user-img {
        height: 40px;
        width: 40px;
        border-radius: 50%;
        background: #EAECF0;
    }
</style>
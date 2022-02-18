<template>
    <nav class="navbar flex mx-7rem">
        <div class="flex">
            <Logo />
            <ul class="flex">
                <li>
                    <NuxtLink to="">Home</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Dashboard</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Projects</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Tasks</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Reporting</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Users</NuxtLink>
                </li>
            </ul>
        </div>
        <UserProfileNav  class="user"/>
    </nav>
</template>
<style scoped>
    .navbar {
        --gap: 1.688rem;
        align-items: center;
        justify-content: space-between;
        margin-block: 1rem;
    }

    ul {
        --gap: 1.688rem;
        list-style: none;
        align-items: center;
    }

    .user {
        float: right;
    }
</style>
<style>
    .v-application a {
        color: inherit;
    }
</style>
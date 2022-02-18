<template>
    <nav class="navbar flex">
            <ul class="flex">
                <li>
                    <NuxtLink to="">Overview</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Notifications</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Analytics</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Saved reports</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">Trade history</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="">User reports</NuxtLink>
                </li>
            </ul>
            <Search startIcon="search" />
    </nav>
</template>
<style scoped>
    .navbar {
        --gap: 1.688rem;
        align-items: center;
        margin-block: 10px;
    }

    ul {
        --gap: 1.688rem;
        list-style: none;
        align-items: center;
    }
    li {
        height: max-content
    }
</style>
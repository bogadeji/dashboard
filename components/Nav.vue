<template>
    <div>
        <nav class="navbar flex mx-comp">
            <div class="flex">
                <Logo />
                <ul class="flex desktop-only">
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
            <UserProfileNav  class="user desktop-and-tablet"/>
            <button class="outline hamburger-btn mobile-and-tablet"><span class="hamburger"></span></button>
        </nav>
        <hr />
    </div>
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
    .hamburger {
        width: 15px;
        display: block;
        position: relative;
    }
    .hamburger,
    .hamburger::before,
    .hamburger::after {
        height: 2px;
        background: hsla(220, 13%, 46%, 1);
    }
    .hamburger::before,
    .hamburger::after {
        content: '';
        position: absolute;
        left: 0;
        right: 0;
        width: 18px;
    }

    .hamburger::before {
        top: 5px;
    }

    .hamburger::after {
        bottom: 5px;
    }

</style>
<style>
    .v-application a {
        color: hsla(217, 23%, 27%, 1) !important;
    }
</style>
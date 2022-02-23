<template>
    <div class="search flex">
        <span class="material-icons start-icon">search</span>
        <input placeholder="Search" />
    </div>
</template>
<style scoped>
    .search {
        --gap: 5px;
        border: 1px solid hsla(216, 16%, 84%, 1);
        border-radius: 8px;
        align-items: center;
        padding: 10px 14px;
        width: 320px;
        max-width: 320px;
        color : #667085
    }
    span.material-icons.start-icon {
        font-size: 25px;
    }
    .search input {
        border: none;
    }
    .search input:focus {
        outline: #fff;
    }
</style>
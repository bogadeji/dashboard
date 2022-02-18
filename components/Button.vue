<template>
        <button :class="{ 'outline': outline, 'primary': primary}" class="base-button flex">
            <slot>Button</slot>
        </button>
</template>
<script>
export default {
    name: 'Button',
    props: {
                outline: {
                    type: Boolean,
                    default: false
                },
                primary: {
                    type: Boolean,
                    default: false
                },
            },
    data() {
        return {
            
        }
    }
}
</script>
<style scoped>
    .base-button {
        padding: 0.625rem 1rem;
        --gap: 1rem;
        align-items: center;
        font-size: var(--fs, 14px);
        border-radius: 8px;
        max-width: max-content;
    }
    .base-button.outline {
        background-color: hsla(0, 0%, 100%, 1);
        box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
        border: 1px solid hsla(216, 16%, 84%, 1);
        color: hsla(217, 23%, 27%, 1)
    }
    .base-button.primary {
        background: hsla(259, 63%, 59%, 1);
        box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
        color: hsla(0, 0%, 100%, 1);
        border: unset;
    }
</style>

<template>
    <a href="#!" class="gold__link">{{ linkText }}</a>
</template>

<script>
export default {
    name: 'Link',
    props: {
        linkText: {
            type: String,
            default: 'free stuff'
        }
    }
}
</script>

<style lang="scss" scoped>

.gold__link {
    max-width: 170px;
    min-width: 170px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: var(--gold-gradient);
    border-radius: 5px;
    color: var(--body-color);
    line-height: 270%;
    text-transform: uppercase;
    font-weight: 500;
    font-size: calc(14px + 4 * (100vw / 1920));
}

@media (min-width: 1920px) {
    .gold__link {
        font-size: 18px !important;
    }
}

@media (max-width: 320px) {
    .gold__link {
        font-size: calc(14px + (4 + 4 * 0.7) * ((100vw - 320px)/ 1920));
    }
}
</style>
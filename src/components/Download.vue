<template>
    <a href="#!" class="download__link"><i class="far fa-download"></i> {{ linkText }}</a>
</template>

<script>
export default {
    name: "Download Link",
    props: {
        linkText: {
            type: String,
            default: "download"
        }
    }
}
</script>

<style lang="scss" scoped>

.download__link {
    max-width: max-content;
    width: 100%;
    display: flex;
    align-items: center;
    column-gap: 5px;
    background: var(--gold-gradient);
    border-radius: 5px;
    padding: 15px 15px;
    color: #0d0d0d;
    text-transform: uppercase;
    font-weight: 600;
    font-size: calc(13px + 3 * (100vw / 1920));
}

@media (max-width: 1920px) {
    .download__link {
        font-size: 16px !important;
    }
}

@media (max-width: 320px) {
    .download__link {
        font-size: calc(13px + (3 + 3 * 0.7) * ((100vw - 320px)/ 1920));
    }
}

</style>
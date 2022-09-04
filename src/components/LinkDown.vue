<template>
  <a href="#works" class="gold-link-down"> {{ linkText }} <i class="fas fa-chevron-down"></i></a>
</template>

<script>

export default {
    name: "Link Down",
    props: {
        linkText: {
            type: String,
            default: 'works'
        }
    }
}

</script>

<style lang="scss" scoped>
.gold-link-down {
    max-width: 180px;
    min-width: 180px;
    width: 100%;
    display: flex;
    gap: 8px;
    justify-content: center;
    align-items: center;
    background: linear-gradient(295.38deg, #FFE5A2 4.89%, #BF841A 50.44%, #FFCD74 95.06%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-size: calc(14px + 4 * (100vw / 1920));
    line-height: 270%;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    border-width: 2px;
    border-style: solid;
    border-image: linear-gradient(165deg, rgba(255, 225, 149, 1), rgba(242, 187, 90, 0.8768), rgba(191, 122, 0, 0.75), rgba(191, 122, 0, 0), rgba(15, 18, 24, 0),
     rgba(143, 168, 255, 0.2), rgba(0, 0, 0, 0)) 1;
    transition: 1s;

    &:hover {
        border-image: linear-gradient(360deg, rgba(255, 225, 149, 1), rgba(242, 187, 90, 0.8768), rgba(191, 122, 0, 0.75), rgba(191, 122, 0, 0), rgba(15, 18, 24, 0),
     rgba(143, 168, 255, 0.2), rgba(0, 0, 0, 0)) 1;
    }
}

@media (min-width: 1920px) {
    .gold-link-down {
        font-size: 18px !important; 
    }
}

@media (max-width: 320px) {
    .gold-link-down {
        font-size: calc(14px + (4 + 4 * 0.7) * ((100vw - 320px)/ 1920));
    }
}

</style>
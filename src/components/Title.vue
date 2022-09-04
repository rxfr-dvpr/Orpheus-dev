<template>
  <h2 :class="`${sectionName}__title`" v-if="!linkAlso">{{ titleText }}</h2>

  <div :class="`rx__title-box ${sectionName}__title-box`" v-else>
      <h2 :class="`${sectionName}__title`">{{ titleText }}</h2>

      <span class="gold-line"></span>

      <a href="#!" :class="`${sectionName}__view-link`">{{ linkText }}</a>
  </div>
</template>

<script>
export default {
    name: "Title",
    props: {
        titleText: {
            type: String,
            default: "title"
        },
        sectionName: {
            type: String,
            default: "section"
        },
        linkText: {
            type: String,
            default: 'view more'
        },
        linkAlso: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style lang="scss" scoped>
h2 {
    font-size: calc(20px + 8 * (100vw / 1920));
    color: var(--gold-gradient);
    text-transform: uppercase;
    font-weight: 800;
}

.rx__title-box {
    display: flex;
    align-items: center;
    column-gap: 25px;
    row-gap: 15px;
    
    a {
        font-size: calc(15px + 2 * (100vw / 1920));
        text-transform: uppercase;
        color: var(--text-color);
        transition: .4s;

        &:hover {
            color: #BF841A;
        }
    }

    .gold-line {
        width: 2px;
        height: 25px;
        background: linear-gradient(295.38deg, #FFE5A2 4.89%, #BF841A 50.44%, #FFCD74 95.06%);
    }
}

@media (min-width: 1920px) {

    h2 {
        font-size: 28px !important;
    }

    .rx__title-box { 
        a {
            font-size: 17px !important;
        }
    }
}

@media (max-width: 414px) {
    .rx__title-box {
        flex-direction: column;

        .gold-line {
            width: 25px !important;
            height: 2px !important;
        }
    }
}

@media (max-width: 320px) {

    h2 {
        font-size: calc(20px + (8 + 8 * 0.7) * ((100vw - 320px)/ 1920));
    }

    .rx__title-box { 
        a {
            font-size: calc(15px + (2 + 2 * 0.7) * ((100vw - 320px)/ 1920));
        }
    }
}

</style>
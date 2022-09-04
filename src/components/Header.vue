<template>
  <header class="header">
    <div class="container">
        <div class="row">
            <div class="header__desc">
                <h1 class="header__desc-title">{{ title }}</h1>

                <p class="header__desc-text">{{ text }}</p>

                <div class="header__desc-links">
                    <LinkDown/>
                    <Link/>
                </div>
            </div>

            <img :src="lightTheme ? imgLight : imgDark" alt="" class="header__img">
        </div>
    </div>
  </header>
</template>

<script>
import LinkVue from './Link.vue'
import LinkDownVue from './LinkDown.vue'

export default {
    name: "Header",
    data() {
        return {
            imgDark: require('@/assets/img/header/header-sculpture.png'),
            imgLight: require('@/assets/img/header/header-sculpture-2.png'),
            title: 'yet the story of orpheus',
            text: 'product & graphic designer, with experience in delivering end-to-end ux/ui design for software products.',
        }
    },
    props: {
        lightTheme: {
            type: Boolean,
            default: false
        }
    },
    components: {
        Link: LinkVue,
        LinkDown: LinkDownVue
    }

}
</script>

<style lang="scss" scoped>
.header {
    width: 100%;
    padding: 160px 0 40px;
    overflow-x: hidden;

    .row {
        justify-content: space-between;
        position: relative;
        flex-wrap: unset;

        &::before {
            content: '';
            max-width: 800px;
            width: 100%;
            position: absolute;
            top: 20%;
            left: -25%;
            background: radial-gradient(58.12% 110.04% at 46.74% -1.76%, rgba(143, 191, 253, 0.5) 0%, rgba(38, 72, 122, 0.6) 29.63%, rgba(15, 18, 24, 0) 100%);
            filter: blur(128px);
            opacity: 0.7;
            max-height: 300px;
            height: 100%;
            z-index: -1;
        }

        &::after {
            content: '';
            max-width: 800px;
            width: 100%;
            position: absolute;
            top: -50%;
            right: -25%;
            background: radial-gradient(58.12% 110.04% at 46.74% -1.76%, rgba(143, 191, 253, 0.5) 0%, rgba(38, 72, 122, 0.6) 29.63%, rgba(15, 18, 24, 0) 100%);
            filter: blur(128px);
            opacity: 0.7;
            transform: rotate(-90deg);
            max-height: 300px;
            height: 100%;
            z-index: -1;
        }
    }

    &__desc {
        max-width: 550px;
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        row-gap: 35px;
        
        &-title {
            font-size: calc(30px + 34 * (100vw / 1920));
            font-weight: 600;
            text-transform: uppercase;
        }

        &-text {
            color: var(--primary-color);
            font-size: calc(15px + 7 * (100vw / 1920));
            text-align: justify;
            text-transform: capitalize;
            line-height: 40px;
        }

        &-links {
            width: 100%;
            display: flex;
            column-gap: 50px;
            align-items: center;
            flex-wrap: wrap;
            row-gap: 30px;
        }
    }

    &__img {
        max-width: 750px;
        width: 100%;
        object-fit: cover;
        z-index: -1;
    }
}

@media (min-width: 1920px) {
    .header {
        &__desc {
            &-title {
                font-size: 64px !important;
            }
            &-text {
                font-size: 22px !important;
            }
        }
    }
}   

@media (max-width: 1330px) {
    .header {
        &__img {
            max-width: 600px;
        }
    }
}

@media (max-width: 1024px) {
    .header {
        &__img {
            max-width: 550px;
        }

        .row {
    
            &::before {
                display: none;
            }

            &::after {
                display: none;
            }
        }
    }
}

@media (max-width: 992px) {
    .header  {
        .row {
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            row-gap: 30px;
        }

        &__desc {
            align-items: center;
            text-align: center;

            &-text {
                text-align: center;
            }

            &-links {
                justify-content: center;
            }
        }
    }
}

@media (max-width: 320px) {
    .header {
        &__desc {
            
            &-title {
                font-size: calc(30px + (34 + 34 * 0.7) * ((100vw - 320px)/ 1920));
            }
            &-text {
                font-size: calc(15px + (7 + 7 * 0.7) * ((100vw - 320px)/ 1920));
            }
        }
    }
}

</style>
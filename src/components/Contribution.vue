<template>
    <section class="contribution__section" id="contribution">
        <div class="container">
            <div class="row">
                <Title :linkAlso="true" sectionName="contribution" :titleText="title"/>

                <div class="contribution__content">
                    <img :src="lightTheme ? img2 : img1" alt="" class="contribution__content-img">

                    <div class="contribution__desc">
                        <h3 class="contribution__desc-title">{{ descTitle }}</h3>
                        <p class="contribution__desc-text">{{ descText }}</p>

                        <Download/>
                    </div>
                </div>

                <div class="contribution__avatars-content" id="community">
                    <div class="contribution__avatars-desc">
                        <h3 class="contribution__avatars-desc-title">{{ avatarsTitle }}</h3>
                        <p class="contribution__avatars-desc-text">{{ avatarsText }}</p>

                        <Download/>
                    </div>

                    <div class="avatars__images">
                        <img src="@/assets/img/main/avatars/avatar-1.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-2.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-3.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-4.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-5.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-6.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-7.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-8.png" alt="" class="avatars__img">
                        <img src="@/assets/img/main/avatars/avatar-9.png" alt="" class="avatars__img">
                        
                    </div>
                </div>

            </div>
        </div>
    </section>

</template>

<script>
import DownloadVue from './Download.vue'
import TitleVue from './Title.vue'

export default {
    name: "Contribution",
    data() {
        return {
            title: 'contribution',
            descTitle: "3d greek statue pack",
            descText: 'over 200 greek style sculpture',
            avatarsTitle: "greek statue avatars",
            avatarsText: '+500 greek style user avatars',
            img1: require('@/assets/img/main/contribution/content-img.png'),
            img2: require('@/assets/img/main/contribution/content-img-2.png'),
        }
    },
    components: {
        Title: TitleVue,
        Download: DownloadVue
    },
    props: {
        lightTheme: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style lang="scss" scoped>

@keyframes infinityImage {
    from {
        transform: translateY(25%);
    }
    to {
        transform: translateY(-25%);
    }
}

.contribution__section {
    width: 100%;
    padding: 40px 0;

    .row {
        flex-direction: column;
        align-items: flex-start;
        row-gap: 45px;
    }

    .contribution__content {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 30px;
        padding-right: 50px;

        &-img {
            max-width: 800px;
            width: 100%;
            object-fit: cover;
            max-height: 380px;
            height: 100%;
        }

        .contribution__desc {
            max-width: 600px;
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            row-gap: 25px;
            z-index: 3;

            &-title {
                font-size: calc(30px + 12 * (100vw / 1920));
                font-weight: 700;
            }

            &-text {
                font-size: calc(18px + 14 * (100vw / 1920));
                color: var(--text-color);
                text-transform: uppercase;
                letter-spacing: 0.285em;
            }
        }
    }

    .contribution__avatars-content {
        width: 100%;
        max-height: 430px;
        height: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 30px;
        padding-left: 50px;
        overflow: hidden;

        &-img {
            max-width: 800px;
            width: 100%;
            object-fit: cover;
            max-height: 380px;
            height: 100%;
        }

        .contribution__avatars-desc {
            max-width: 600px;
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            row-gap: 25px;
            z-index: 3;

            &-title {
                font-size: calc(30px + 12 * (100vw / 1920));
                font-weight: 700;
            }

            &-text {
                font-size: calc(18px + 14 * (100vw / 1920));
                color: var(--text-color);
                text-transform: uppercase;
                letter-spacing: 0.285em;
            }
        }
    }

    .avatars__images {
        max-width: 800px;
        width: 100%;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 40px;
        animation: infinityImage 5s linear infinite alternate;

        .avatars__img {
            width: 100%;
            border-radius: 90px;
            overflow: hidden;
        }
    }
}

@media (min-width: 1920px) {
    .contribution__desc {
        &-title {
            font-size: 42px !important;
        }

        &-text {
            font-size: 32px !important;
        }
    }

    .contribution__avatars-desc {
        &-title {
            font-size: 42px !important;
        }

        &-text {
            font-size: 32px !important;
        }
    }
}

@media (max-width: 1330px) {
    .contribution__content {
        &-img {
            max-width: 600px !important;
        }
    }
}

@media (max-width: 992px) {
    .contribution__section {
        .row {
            align-items: center;
        }
    }

    .contribution__content {
        flex-direction: column;
        justify-content: flex-start;
        padding-right: 0 !important;

        &::after {
            display: none;
        }
    }

    .contribution__avatars-content {
        flex-direction: column;
        justify-content: flex-start;
        padding-left: 0 !important;
        margin-top: 45px;
        background: transparent !important;

        .avatars__images {
            animation: unset;
            gap: 20px;
        }

        &::after {
            display: none;
        }
    }
}

@media (max-width: 320px) {

    .contribution__desc {
        &-title {
            font-size: calc(30px + (12 + 12 * 0.7) * ((100vw - 320px)/ 1920)) !important;

        }

        &-text {
            font-size: calc(18px + (14 + 14 * 0.7) * ((100vw - 320px)/ 1920)) !important;
        }
    }

    .contribution__avatars-desc {
        &-title {
            font-size: calc(30px + (12 + 12 * 0.7) * ((100vw - 320px)/ 1920)) !important;
        }

        &-text {
            font-size: calc(18px + (14 + 14 * 0.7) * ((100vw - 320px)/ 1920)) !important;
        }
    }
}


</style>
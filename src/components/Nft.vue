<template>
    <section class="nft__section" id="works">
        <div class="container">
            <div class="row">
                <Title :linkAlso="true" sectionName="nft" titleText="recent nft"/>

                <div class="nft__slider">
                    <swiper class="nft__section-swiper" :speed="500" :grabCursor="true" 
                    :breakpoints="breakPoints" :modules="modules" navigation>
                        <swiper-slide class="nft__slide" v-for="(slide, idx) in slider" :key="idx">
                            <img :src="slide.img" alt="" class="nft__slide-img">

                            <div class="nft__slide-desc">
                                <p class="nft__slide-text">{{ slide.text }}</p>
                            </div>
                        </swiper-slide>
                    </swiper>
                </div>
                
            </div>
        </div>
    </section>
</template>

<script>
import TitleVue from './Title.vue'

import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation } from 'swiper';

import 'swiper/scss';
import 'swiper/scss/navigation';


export default {
    name: "Nft Section",
    components: {
        Title: TitleVue,
        Swiper,
        SwiperSlide
    },
    data() {
        return {
            slider: [
                {
                    img: require('@/assets/img/main/nft/mortal1.png'),
                    text: 'relics of a mortal past 1 - NFT'
                },
                {
                    img: require('@/assets/img/main/nft/mortal2.png'),
                    text: 'relics of a mortal past 2 - NFT'
                },
                {
                    img: require('@/assets/img/main/nft/mortal3.png'),
                    text: 'relics of a mortal past 3 - NFT'
                },
                {
                    img: require('@/assets/img/main/nft/mortal4.png'),
                    text: 'relics of a mortal past 4 - NFT'
                },
                {
                    img: require('@/assets/img/main/nft/mortal5.png'),
                    text: 'relics of a mortal past 5 - NFT'
                }
            ],
            breakPoints: {
                1170: {
                    slidesPerView: 3,
                    spaceBetween: 75
                }, 
                1024: {
                    slidesPerView: 2,
                    spaceBetween: 75
                },
                768: {
                    slidesPerView: 2,
                    spaceBetween: 50
                }
            },
            modules: [Navigation]
        }
    },
}
</script>

<style lang="scss" scoped>
.nft__section {
    width: 100%;
    padding-bottom: 40px;

    .row {
        flex-direction: column;
        align-items: flex-end;
        row-gap: 35px;
    }

    .nft__slider {
        width: 100%;
    }

    &-swiper {
        width: 100%;
        padding-bottom: 80px;

        .nft__slide {
            width: 100%;
            color: var(--primary-color);
            position: relative;
            max-height: 350px;
            height: 100%;
            border-width: 2px;
            border-style: solid;
            border-image: linear-gradient(135deg, rgba(255, 225, 149, 1), rgba(191, 122, 0, 0.75), rgba(191, 122, 0, 0), rgba(191, 122, 0, 0), rgba(15, 18, 24, 0),
           rgba(0, 0, 0, 0)) 1;
           overflow: hidden;

            &-img {
                width: 100%;
                max-height: 350px;
                height: 100%;
                object-fit: cover;
                transition: .4s;
            }

            &-desc {
                position: absolute;
                bottom: 0;
                left: 0;
                width: 100%;
                padding: 15px 20px;
                z-index: 3;
                background: linear-gradient(90deg, rgba(9, 11, 14, 0.81) 19.79%, rgba(9, 11, 14, 0) 97.4%);
                transition: .4s;
            }

            &-text {
                font-size: 18px;
                font-weight: 500;
                color: var(--primary-color);
                text-transform: capitalize;
                transition: .4s;
            }

            &:hover {

                .nft__slide-img {
                    transform: scale(1.2);
                }

                .nft__slide-desc {
                    bottom: -15%;
                }
            }
        }
    }
}

@media (max-width: 992px) {
    .nft__section {
        .row {
            align-items: center;
        }
    }
}
</style>
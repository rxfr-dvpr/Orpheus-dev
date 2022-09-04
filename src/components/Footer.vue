<template>
    <footer class="footer" id="get in touch">
        <div class="container">
            <div class="row">
                
                <div class="footer__content">
                    <h3 class="footer__content-title">
                        {{ title }}
                    </h3>
                    
                    <p class="footer__content-text">{{ text }}</p>

                    <div class="footer__content-links">
                        <a href="#!" class="footer__link" v-for="(link, idx) in footerLinks" :key="idx" v-html="link.icon"></a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import TitleVue from './Title.vue'

export default {
    name: "Footer",
    components: {
        Title: TitleVue
    },
    data() {
        return {
            title: "let's connect",
            text: 'Get in touch for opportunities or just to say hi! 👋',
            footerLinks: [
                {
                    icon: '<i class="fab fa-linkedin-in"></i>'
                },
                {
                    icon: '<i class="fab fa-dribbble"></i>'
                },
                {
                    icon: '<i class="fab fa-instagram"></i>'
                },
                {
                    icon: '<i class="fab fa-medium-m"></i>'
                },
                {
                    icon: '<i class="far fa-envelope"></i>'
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
.footer {
    padding: 100px 0;

    &__content {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        row-gap: 10px;
        text-align: center;

        &-title {
            font-size: calc(20px + 8 * (100vw / 1920));
        }

        &-text {
            font-size: calc(15px + 3 * (100vw / 1920));
            color: var(--text-color);
            text-transform: uppercase;
        }

        &-links {
            display: flex;
            align-items: center;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
            justify-content: center;

            .footer__link {
                background: linear-gradient(295.38deg, #FFE5A2 4.89%, #BF841A 50.44%, #FFCD74 95.06%);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                background-clip: text;
                font-size: 32px;
                max-width: 55px;
                min-width: 55px;
                width: 100%;
                min-height: 55px;
                max-height: 55px;
                height: 100%;
                overflow: hidden;
                display: grid;
                place-items: center;
                border-width: 2px;
                border-style: solid;
                border-image: linear-gradient(135deg, rgba(255, 225, 149, 1), rgba(191, 122, 0, 0.6), rgba(191, 122, 0, 0.3), rgba(191, 122, 0, 0),  rgba(191, 122, 0, 0), rgba(15, 18, 24, 0),
              rgba(0, 0, 0, 0)) 1;
                transition: border-image .5s;

              &:hover {
                border-image: linear-gradient(365deg, rgba(255, 225, 149, 1), rgba(191, 122, 0, 0.6), rgba(191, 122, 0, 0.3), rgba(191, 122, 0, 0),  rgba(191, 122, 0, 0), rgba(15, 18, 24, 0),
              rgba(0, 0, 0, 0)) 1;
              }
            }
        }
    }
}

@media (min-width: 1920px) {

    .footer__content-title {
        font-size: 28px;
    }

    .footer__content-text {
        font-size: 18px;
    }
}

@media (max-width: 320px) {

    .footer__content-title {
        font-size: calc(20px + (8 + 8 * 0.7) * ((100vw - 320px)/ 1920));
    }

    .footer__content-text {
        font-size: calc(15px + (3 + 3 * 0.7) * ((100vw - 320px)/ 1920));
    }
}

</style>
<template>
  <nav class="nav">
    <div class="container">
        <div class="row">
            <a href="" class="logo"><img :src="lightTheme ? logoLight : logoDark" alt="" class="logo-img"></a>

            <div class="nav__collapse" :class="{opened: navOpened}">
                <ul class="nav__list">
                    <li class="nav__list-item" v-for="(link, idx) in navLinks" :key="idx">
                        <a :href="`#${link}`" class="nav__list-link">{{ link }}</a>
                    </li>
                
                    <button class="theme-changer-btn" @click="$emit('themeChange')" :class="{'anim-rotate': !lightTheme}">
                        <i class="far fa-moon" v-if="lightTheme"></i>
                        <i class="fal fa-sun" v-else></i>                    
                    </button>
                </ul>
            </div>

            <button class="nav__btn" @click="navOpened = !navOpened" :class="[{'light-theme': lightTheme}, {'nav-opened': navOpened}]">
                <span class="nav__btn-line"></span>
                <span class="nav__btn-line"></span>
                <span class="nav__btn-line"></span>
            </button>
            
        </div>
    </div>

    <Transition name="fade">
        <span class="dark-bg" v-show="navOpened" @click="navOpened = false"></span>
    </Transition>
  </nav>
</template>

<script>

export default {
    name: "Nav",
    data() {
        return {
            logoDark: require('@/assets/img/logo.svg'),
            logoLight: require('@/assets/img/logo-light.svg'),
            navLinks: [
                'works',
                'contribution',
                'community',
                'get in touch'
            ],
            navOpened: false
        }
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

.nav {
    width: 100%;
    padding: 20px 0;
    border-bottom: 1px solid #101822;
    backdrop-filter: blur(25px);
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;

    .row {
        justify-content: space-between;
    }

    .logo {
        max-width: 150px;
        width: 100%;
        display: block;

        &-img {
            width: 100%;
        }
    }

    .nav__collapse {
        max-width: max-content;
        width: 100%;
    }

    &__list {
        width: 100%;
        display: flex;
        column-gap: 30px;
        align-items: center;

        &-link {
            padding: 5px;
            font-size: 16px;
            color: var(--primary-color);
            text-transform: capitalize;
            font-weight: 500;
            transition: .4s;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            row-gap: 2px;

            &::after {
                content: '';
                width: 0;
                height: 2px;
                background: var(--gold-gradient);
                border-radius: 100px;
                transition: .5s;
            }

            &:hover::after {
                width: 100%;
            }
        }
    }

    .theme-changer-btn {
        border: none;
        border-radius: 50%;
        background: transparent;
        font-size: 22px;
        color: var(--primary-color);
        cursor: pointer;
        width: 30px;
        height: 30px;
        display: grid;
        place-items: center;
        padding-top: 1.5px;
        transition: 1s;

        &.anim-rotate:hover {
            transform: rotate(360deg);
        }
    }

    .user__lang {
        background: transparent;
        color: var(--primary-color);
        border: none;
        cursor: pointer;
        outline: none;
        font-size: 15px;

        & option {
            background: var(--third-color);
            border: none;
            cursor: pointer;
        }
    }

    &__btn {
        display: none;
    }
}

@media (max-width: 992px) {
    .nav {
        border-bottom: 0 !important;

        &__collapse {
            position: fixed;
            top: 0;
            right: 0;
            height: 100vh;
            display: flex;
            justify-content: flex-end;
            align-items: center;
            padding: 85px 10px 10px;
            z-index: -1;
            transform: translateX(100%);
            transition: .3s;
            background: var(--third-color);

            .nav__list {
                max-width: max-content;
                flex-direction: column;
                align-items: flex-end;
                row-gap: 15px;
                overflow-y: auto;
            }

            &.opened {
                transform: translateX(0);
            }
        }

        .nav__btn {
            width: 30px;
            height: 100%;
            max-height: max-content;
            border: none;
            background: transparent;
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            row-gap: 6px;

            &-line {
                width: 100%;
                height: 3px;
                background: var(--primary-color);
                border-radius: 50px;
                transition: .3s;
                border-radius: 10px;
            }

            &-line:nth-of-type(2) {
                width: 75%;
            }

            &-line:last-of-type {
                width: 60%;
            }

            &.light-theme {
                .nav__btn-line {
                    background: var(--body-color);
                }
            }

            &.nav-opened {
                .nav__btn-line:last-of-type {
                    width: 100%;
                }
            }
        }

        .dark-bg {
            width: 100%;
            height: 100vh;
            position: absolute;
            top: 0;
            left: 0;
            background: rgba($color: #000, $alpha: 0.5);
            z-index: -2;
            transition: .4s;
        }
    }

    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.5s;
    }

    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }
}

</style>
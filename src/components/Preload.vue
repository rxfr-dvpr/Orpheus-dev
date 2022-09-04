<template>
    <div class="preloader">
        <div class="preloader__content">
            <img :src="womanImg" alt="" class="preloader-icon">
            <img src="@/assets/img/preloader/rotatableGoldLine.svg" alt="" class="preloader-gold-line">
        </div>
    </div>
</template>

<script>
export default {
    name: "Preload",
    data() {
        return {
            womanImg: require('@/assets/img/woman-logo.svg')      
        }
    },
    mounted() {
        
        let preloader = document.querySelector('.preloader');
        preloader.classList.add('active')
        setTimeout(() => {
            preloader.classList.remove('active')
        }, 3500);
    }
}
</script>

<style lang="scss" scoped>

@keyframes rotateBorder {
    from {
        transform: rotate(0);
    }
    to {
        transform: rotate(360deg);
    }
}

.preloader {
    width: 100%;
    min-height: 100vh;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background: var(--body-color);
    display: none;
    place-items: center;
    z-index: 20000;

    &__content {
        max-width: 95px;
        min-width: 95px;
        width: 100%;
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;
        row-gap: 2px;

        .preloader-icon {
            max-width: 60px;
            min-width: 60px;
            width: 100%;
        }

        .preloader-gold-line {
            position: absolute;
            top: -15px;
            left: 0;
            z-index: -1;
        }
    }

    &.active {
        display: grid;

        .preloader-gold-line {
            animation: rotateBorder 0.7s linear infinite;
        }

        body {
            overflow: hidden;
        }
    }
}
</style>
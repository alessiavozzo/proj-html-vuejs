<script>
import { navLinks } from './assets/js/links-icons';
import { footerCols } from './assets/js/links-icons';
import { icons } from './assets/js/links-icons';
import "vue3-carousel/dist/carousel.css";

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    name: "App",
    data() {
        return {
            navLinks: navLinks,
            footerCols: footerCols,
            icons: icons
        }
    },
    components: {
        AppHeader,
        AppMain,
        AppFooter
    }
}
</script>

<template>
    <AppHeader :navLinks="navLinks" :icons="icons" />
    <AppMain />
    <AppFooter :footerCols="footerCols" :icons="icons" />
</template>

<style>
#app {
    .carousel__pagination-button::after {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        background-color: var(--primary-lighter);
    }

    .carousel__pagination-button--active::after {
        background-color: var(--academy-primary);
    }

    .carousel__pagination {
        margin-top: 2.5rem;
    }

    .carousel__next {
        right: -2.5rem;
    }

    .carousel__prev {
        left: -2.5rem;
    }

    .carousel__icon {
        color: var(--primary-lighter);

        &:hover {
            color: var(--academy-primary);
        }
    }
}
</style>

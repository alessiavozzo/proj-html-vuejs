<script>
import { navLinks } from './assets/js/links-icons';
import { footerCols } from './assets/js/links-icons';
import { icons } from './assets/js/links-icons';

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

<style scoped></style>

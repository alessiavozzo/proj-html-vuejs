<script>
import { navLinks } from './assets/js/links-icons';
import { navIcons } from './assets/js/links-icons';
import { footerCols } from './assets/js/links-icons';
import { socialIcons } from './assets/js/links-icons';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    name: "App",
    data() {
        return {
            navIcons: navIcons,
            navLinks: navLinks,
            footerCols: footerCols,
            socialIcons: socialIcons
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
    <AppHeader :navLinks="navLinks" :navIcons="navIcons" />
    <AppMain />
    <AppFooter :footerCols="footerCols" :socialIcons="socialIcons" />
</template>

<style scoped></style>

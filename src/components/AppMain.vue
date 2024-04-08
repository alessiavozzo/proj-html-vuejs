<script>
import SubjectsSection from './SubjectsSection.vue';

export default {
    name: "AppMain",
    components: {
        SubjectsSection,
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <main id="site_main">
        <!-- subjects section: subject cards -->
        <SubjectsSection />

    </main>
</template>


<style scoped></style>
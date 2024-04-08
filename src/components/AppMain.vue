<script>
import SubjectsSection from './SubjectsSection.vue';
import TutoringSection from './TutoringSection.vue'

export default {
    name: "AppMain",
    components: {
        SubjectsSection,
        TutoringSection
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

        <!-- tutoring section -->
        <TutoringSection />

    </main>
</template>


<style scoped></style>
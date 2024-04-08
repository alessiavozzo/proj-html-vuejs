<script>
import SubjectsSection from './SubjectsSection.vue';
import TutoringSection from './TutoringSection.vue';
import EmpoweringSection from './EmpoweringSection.vue';

export default {
    name: "AppMain",
    components: {
        SubjectsSection,
        TutoringSection,
        EmpoweringSection
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

        <!-- empowering section -->
        <EmpoweringSection />

    </main>
</template>


<style scoped></style>
<script>
import SubjectsSection from './SubjectsSection.vue';
import TutoringSection from './TutoringSection.vue';
import EmpoweringSection from './EmpoweringSection.vue';
import TestimonialsSection from './TestimonialsSection.vue';

export default {
    name: "AppMain",
    components: {
        SubjectsSection,
        TutoringSection,
        EmpoweringSection,
        TestimonialsSection
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

        <!-- Testimonials section -->
        <TestimonialsSection />

    </main>
</template>


<style scoped></style>
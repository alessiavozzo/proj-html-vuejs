<script>
import SubjectsSection from './SubjectsSection.vue';
import TutoringSection from './TutoringSection.vue';
import EmpoweringSection from './EmpoweringSection.vue';
import TestimonialsSection from './TestimonialsSection.vue';
import LearningSection from './LearningSection.vue';
import CoursesSection from './CoursesSection.vue';
import PriceSection from './PriceSection.vue';
import ClientsSection from './ClientsSection.vue';

export default {
    name: "AppMain",
    components: {
        SubjectsSection,
        TutoringSection,
        EmpoweringSection,
        TestimonialsSection,
        LearningSection,
        CoursesSection,
        PriceSection,
        ClientsSection
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

        <!-- Learning section -->
        <LearningSection />

        <!-- Courses section -->
        <CoursesSection />

        <!-- Price table section -->
        <PriceSection />

        <!-- Clients Section -->
        <ClientsSection />

    </main>
</template>


<style scoped></style>
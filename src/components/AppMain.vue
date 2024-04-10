<script>
import SubjectsSection from './main-components/SubjectsSection.vue';
import TutoringSection from './main-components/TutoringSection.vue';
import EmpoweringSection from './main-components/EmpoweringSection.vue';
import TestimonialsSection from './main-components/TestimonialsSection.vue';
import LearningSection from './main-components/LearningSection.vue';
import CoursesSection from './main-components/CoursesSection.vue';
import PriceSection from './main-components/PriceSection.vue';
import ClientsSection from './main-components/ClientsSection.vue';

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
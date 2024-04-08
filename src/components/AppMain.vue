<script>
import { subjects } from '../assets/js/subjects';
export default {
    name: "AppMain",
    data() {
        return {
            subjects: subjects,
            imageUrl: "/img/h5-custom-icon-"
        }
    }
}
</script>

<template>
    <main id="site_main">

        <section id="subjects">
            <div class="container">
                <div class="row">
                    <div class="card d-flex col-2" v-for="subject in subjects">
                        <img :src="`${imageUrl}${subject.image}`" alt="subject-icon">
                        <h3>{{ subject.name }}</h3>
                    </div>

                </div>
            </div>
        </section>

    </main>
</template>


<style scoped>
#subjects {
    padding: 3rem 0;

    .card {
        border: 1px solid var(--subject-border);
        padding: 2rem 1rem;
        align-items: center;
        flex-direction: column;
        gap: 1.5rem;
        background-color: var(--academy-subject);
    }
}
</style>
<script>
import { subjects } from '../../assets/js/subjects';

export default {
    name: "SubjectSection",
    data() {
        return {
            subjects: subjects,
            imageUrl: "/img/h5-custom-icon-"
        }
    }
}
</script>


<template>
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
</template>


<style scoped>
#subjects {
    padding: 3.5rem 0;

    .card {
        border: 1px solid var(--subject-border);
        padding: 2rem 1rem;
        align-items: center;
        flex-direction: column;
        gap: 1.5rem;
        background-color: var(--academy-subject);
        transition: all 0.3s;

        &:hover {
            transform: scale(1.1);
            cursor: pointer;
        }
    }
}
</style>
<script>
import { courses } from '../assets/js/courses';

export default {
    name: "CoursesSection",
    data() {
        return {
            courses: courses
        }
    }

}
</script>


<template>
    <section id="courses">
        <div class="container">
            <div class="intro">
                <h2>Popular Online Courses</h2>
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus dolorum placeat illum illo
                    ratione
                    sapiente. Tenetur voluptatum facere ut consequatur.</p>
            </div>
            <div class="row">
                <div class="card col-4" v-for="course in courses">
                    <img class="card-top" :src="`/img/${course.image}`" :alt="course.name">
                    <div class="card-bottom d-flex">
                        <div class="course">
                            <div class="generic-info d-flex">
                                <h3>{{ course.name }}</h3>
                                <span class="badge"
                                    :style="{ 'background-color': course.price === 'free' ? 'var(--academy-warning)' : 'var(--academy-primary)' }">{{
                                        course.price
                                    }}</span>
                            </div>
                            <div class="author">{{ course.author }}</div>
                        </div>
                        <div class="description">{{ course.description }}</div>
                        <div class="info d-flex">
                            <span>{{ course.users }}</span>
                            <span>{{ course.type }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped>
#courses {
    background-image: url(/img/background-pattern.jpg);
    padding: 4rem 0;
    border-bottom: 1px solid var(--subject-border);

    .intro {
        width: 70%;
        margin: 0 auto;
        text-align: center;

        h2 {
            padding-bottom: 1rem;
        }
    }

    .card {
        border: 1px solid var(--subject-border);
        padding: 3rem 0;

        img {
            width: 100%;
        }

        .card-bottom {
            padding: 1.5rem 1rem;
            flex-direction: column;
            gap: 1rem;

            .generic-info {
                justify-content: space-between;
                align-items: center;

                .badge {
                    border-radius: 20px;
                    color: var(--academy-lighter);
                    text-transform: uppercase;
                    padding: 0.3rem 0.5rem;
                }
            }

            .info {
                gap: 1rem;

                span:first-of-type::before {
                    content: "\f007";
                }

                span:last-of-type::before {
                    content: "\f02b";
                }

                span::before {
                    font-family: FontAwesome;
                    padding-right: 0.5rem;
                }

            }
        }
    }
}
</style>
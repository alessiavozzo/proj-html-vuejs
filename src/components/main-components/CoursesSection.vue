<script>
import { courses } from '../../assets/js/courses';

import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

export default {
    name: "CoursesSection",
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation
    },
    data() {
        return {
            courses: courses
        }
    }

}
</script>


<template>
    <section id="courses">
        <div class="container d-flex">

            <!-- intro section -->
            <div class="intro">
                <h2>Popular Online Courses</h2>
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus dolorum placeat illum illo
                    ratione
                    sapiente. Tenetur voluptatum facere ut consequatur.</p>
            </div>

            <!-- carousel for cards - 3 cards per page -->
            <Carousel :itemsToShow="3" :wrapAround="true" :transition="500" :itemsToScroll="3">
                <Slide v-for="(course, index) in courses" :key="index" class="col-4">
                    <div class="card">

                        <!-- top: image -->
                        <img class="card-top" :src="`/img/${course.image}`" :alt="course.name">

                        <!-- bottom: info course -->
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
                </Slide>
                <template #addons>
                    <Pagination />
                    <Navigation />
                </template>
            </Carousel>

        </div>
    </section>
</template>


<style scoped>
#courses {
    background-image: url(/img/background-pattern.jpg);
    padding: 6rem 0 6.5rem 0;
    border-bottom: 1px solid var(--border-elements);
    background-position-y: 50%;

    .container {
        flex-direction: column;
        gap: 6rem;
    }

    .intro {
        width: 70%;
        margin: 0 auto;
        text-align: center;

        h2 {
            padding-bottom: 1rem;
            font-size: 3.5rem;
            font-weight: 600;
        }

        p {
            font-size: 1.3rem;
        }
    }

    .card {
        border: 1px solid var(--subject-border);
        margin: 0 1rem;
        background-color: var(--academy-lighter);

        &:has(h3:hover) {
            border: 1px solid var(--academy-primary);
        }

        h3 {
            cursor: pointer;
        }

        img {
            width: 100%;
        }

        .card-bottom {
            padding: 1.5rem 1rem;
            flex-direction: column;
            gap: 1rem;
            text-align: left;

            .generic-info {
                justify-content: space-between;
                align-items: center;

                .badge {
                    border-radius: 20px;
                    color: var(--academy-lighter);
                    text-transform: uppercase;
                    padding: 0.2rem 0.7rem;
                    font-size: 0.9rem;
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

            .author,
            .description,
            .info {
                color: var(--text-dark);
            }
        }
    }
}
</style>
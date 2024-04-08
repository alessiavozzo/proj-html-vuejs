<script>
import { testimonials } from '../assets/js/testimonials'

export default {
    name: "TestimonialsSection",
    data() {
        return {
            testimonials: testimonials,
            currentTestimonial: 0
        }
    },

    methods: {
        next() {
            this.currentTestimonial++
            if (this.currentTestimonial > this.testimonials.length - 1) {
                this.currentTestimonial = 0
            }
        },
        prev() {
            this.currentTestimonial--
            if (this.currentTestimonial < 0) {
                this.currentTestimonial = this.testimonials.length - 1
            }
        }
    }
}
</script>


<template>
    <section id="testimonials" class="d-flex">
        <div class="testimonial" v-for="(testimonial, testimonialIndex) in testimonials">
            <div class="testimonial-info d-flex" v-if="currentTestimonial === testimonialIndex">
                <img :src="`/img/testimonials-standard-${testimonial.image}`" alt="">
                <div class="feed">{{ testimonial.feed }}</div>
                <div class="name">{{ testimonial.name }}</div>
                <div class="job">{{ testimonial.job }}</div>
            </div>
        </div>
        <div class="controls d-flex">
            <button type="button" class="prev-btn" @click="prev()">
                <i class="fa-solid fa-chevron-left"></i>
            </button>
            <button type="button" class="prev-btn" @click="next()">
                <i class="fa-solid fa-chevron-right"></i>
            </button>
        </div>

    </section>

</template>


<style scoped>
#testimonials {
    background-image: url(/img/h5-parallax-img-1.png);
    height: 680px;
    background-size: cover;
    background-position: center;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;

    .testimonial {
        font-size: 1.5rem;
        width: 70%;
        text-align: center;
        color: var(--academy-lighter);

        .testimonial-info {
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }
    }

    .controls {
        width: 90%;
        justify-content: space-between;
        position: absolute;

        .next-btn,
        .prev-btn {
            font-size: 3rem;
            border: none;
            background-color: transparent;
            color: var(--academy-lighter);
            font-size: 5rem;
        }
    }
}
</style>
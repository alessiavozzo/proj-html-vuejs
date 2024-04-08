<script>
import { options } from '../assets/js/links-icons';

export default {
    name: "LearningSection",
    data() {
        return {
            options: options,
            currentClick: null
        }
    },

    methods: {
        changeOption(index) {
            this.currentClick = index
        }
    }
}
</script>


<template>
    <section id="learning">
        <div class="container">
            <div class="row">
                <div class="options col-4">
                    <ul>
                        <li v-for="(option, index) in options" @click="changeOption(index)"
                            :class="{ active: currentClick === index }">
                            {{ option }}</li>
                    </ul>
                </div>

                <div class="possibilities d-flex col-8">
                    <h2>Learning Possibilities</h2>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolor consequatur
                        in cumque aut a alias?
                        At corporis sunt deleniti maiores quia voluptatem similique cupiditate sed pariatur a, assumenda
                        cum
                        asperiores labore in, earum amet molestias aliquid, delectus ullam tempora provident.
                    </p>
                    <ul>
                        <li>Lorem ipsum dolor sit amet consectetur.</li>
                        <li>Lorem ipsum dolor sit amet consectetur.</li>
                        <li>Lorem ipsum dolor sit amet consectetur.</li>
                        <li>Lorem ipsum dolor sit amet consectetur.</li>
                    </ul>
                    <img src="/img/h12-tabs-icon-1.png" alt="">
                </div>

            </div>
        </div>

    </section>

</template>


<style scoped>
#learning {
    padding: 3rem 0;

    .options {
        ul {
            list-style: none;

            li {
                padding: 1rem;
                border: 1px solid var(--subject-border);
            }
        }
    }

    li.active {
        background-color: var(--academy-subject);
        color: var(--academy-primary);
        border-left: 5px solid var(--academy-primary) !important;
    }

    .possibilities {
        flex-direction: column;
        gap: 1rem;
        padding: 2rem;
        position: relative;

        p {
            padding-bottom: 1.5rem;
        }

        ul {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 1rem;

            li::before {
                content: "\f00c";
                font-family: FontAwesome;
                padding-right: 0.5rem;
                color: var(--academy-primary);
            }
        }

        img {
            width: 100px;
            position: absolute;
            right: 0;
            bottom: 0;
        }
    }
}
</style>
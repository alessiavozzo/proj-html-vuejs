<script>
import { options } from '../../assets/js/details';
import { detailsList } from '../../assets/js/details';

export default {
    name: "LearningSection",
    data() {
        return {
            options: options,
            detailsList: detailsList,
            imgPath: "/img/",
            currentClick: 0
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
                    <h2>{{ detailsList[currentClick].title }}</h2>
                    <p>{{ detailsList[currentClick].description }}</p>
                    <ul>
                        <li v-for="check in detailsList[currentClick].checklist">{{ check }}</li>
                    </ul>
                    <img :src="`${imgPath}${detailsList[currentClick].image}`" alt="">
                </div>

            </div>
        </div>

    </section>

</template>


<style scoped>
#learning {
    padding: 8rem 0;
    border-bottom: 1px solid var(--subject-border);

    .options {
        ul {
            list-style: none;

            li {
                padding: 1.5rem 1rem;
                border: 1px solid var(--border-elements);
                font-weight: bold;
                color: var(--text-dark);
            }
        }
    }

    li.active {
        background-color: var(--bg-light);
        color: var(--academy-primary) !important;
        border-left: 7px solid var(--academy-primary) !important;
    }

    .possibilities {
        flex-direction: column;
        gap: 1rem;
        padding: 2rem;
        position: relative;

        h2 {
            font-size: 3rem;
            font-weight: 600;
        }

        p {
            padding-bottom: 1.5rem;
            font-size: 1.4rem;
            color: var(--text-dark);
        }

        ul {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            font-size: 1.4rem;
            color: var(--text-dark);

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
            right: 2rem;
            bottom: 0;
        }
    }
}
</style>
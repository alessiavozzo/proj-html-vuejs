<script>
export default {
    name: "SectionStructure",
    props: {
        title: String,
        description: String,
        link: Object,
        image: String,
        feeds: Object
    },
    data() {
        return {
            storiesNumber: 168,
            eventsNumber: 347
        }
    }
}
</script>

<template>

    <!-- text -->
    <div class="text d-flex" :class="{ 'col-6': !link }">
        <h2 :style="{ 'width': link ? '50%' : '100%' }">{{ title }}</h2>
        <p>{{ description }}</p>
        <a v-if="link" :href="link.href">{{ link.name }}</a>
        <div v-else class="counters d-flex">
            <div class="user-stories d-flex col-6">
                <div class="number">{{ storiesNumber }}</div>
                <span>{{ feeds.stories }}</span>
            </div>
            <div class="events d-flex col-6">
                <div class="number">{{ eventsNumber }}</div>
                <span>{{ feeds.events }}</span>
            </div>
        </div>
    </div>

    <!-- img -->
    <div class="image" :class="{ 'col-6': !link }" :style="{ 'order': !link ? '-1' : '1' }">
        <img :src="`/img/${image}`" :alt="title">
    </div>
</template>


<style scoped>
.text {
    flex-direction: column;
    padding: 1.5rem;
    gap: 1rem;

    h2 {
        font-size: 3rem;
        font-weight: 600;
    }

    p {
        font-size: 1.2rem;
    }

    a {
        font-weight: bold;
        text-transform: uppercase;
        color: var(--academy-primary);
    }
}

img {
    width: 100%;
}

.counters {

    .user-stories,
    .events {
        flex-direction: column;
        gap: 0.5rem;
        font-weight: bold;
        color: var(--academy-primary);

        .number {
            font-size: 3.5rem;
        }

        span {
            font-size: 1.5rem;
        }
    }
}
</style>
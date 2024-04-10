<script>
import SectionStructure from './SectionStructure.vue'
export default {
    name: "TutoringSection",
    components: {
        SectionStructure
    },
    data() {
        return {
            sectionData: {
                title: "The Trusted Name for In-Home Tutoring.",
                paragraph: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis fugit fugiat voluptatem eum cum minus similique ex natus distinctio est in maxime ipsa dolores ratione quas quis vero.",
                imagePath: "h5-img-1.jpg",
                link: {
                    href: "#",
                    name: "Learn more"
                }
            }
        }
    }
}
</script>


<template>
    <section id="tutoring">
        <div class="container">


            <SectionStructure :title="sectionData.title" :description="sectionData.paragraph"
                :image="sectionData.imagePath" :link="sectionData.link" />

        </div>
    </section>

</template>

<style scoped>
#tutoring {
    padding: 1rem 0;
}
</style>
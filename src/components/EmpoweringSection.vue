<script>
import SectionStructure from './SectionStructure.vue'

export default {
    name: "EmpoweringSection",
    components: {
        SectionStructure
    },
    data() {
        return {
            sectionData: {
                title: "Empowering Children to Reach Their Potential",
                paragraph: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis fugit fugiat voluptatem eum cum minus similique ex natus distinctio est in maxime ipsa dolores ratione quas quis vero, sint quia eius.",
                imagePath: "h5-img-2.jpg",
                feeds: {
                    stories: "User stories",
                    events: "Events"
                }
            }
        }
    }
}
</script>


<template>
    <section id="empowering">
        <div class="container">
            <div class="row">

                <SectionStructure :title="sectionData.title" :description="sectionData.paragraph"
                    :image="sectionData.imagePath" :feeds="sectionData.feeds" />
            </div>


        </div>
    </section>

</template>


<style scoped>
#empowering {
    padding: 3rem 0;
}
</style>
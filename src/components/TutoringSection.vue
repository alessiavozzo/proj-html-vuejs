<script>
export default {
    name: "TutoringSection"
}
</script>


<template>
    <section id="tutoring">
        <div class="container">
            <div class="text d-flex">
                <h2>The Trusted Name for In-Home Tutoring.</h2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis fugit fugiat voluptatem eum cum
                    minus similique ex natus distinctio est in maxime ipsa dolores ratione quas quis vero, sint quia
                    eius at optio quibusdam officia consequatur. Consequatur ipsam sequi veniam!</p>
                <a href="#">Learn more</a>
            </div>
            <div class="image">
                <img src="/img/h5-img-1.jpg" alt="students-looking-up">
            </div>

        </div>
    </section>

</template>


<style scoped>
#tutoring {
    padding: 1rem 0;

    .text {
        flex-direction: column;
        gap: 1rem;
        padding-bottom: 2rem;

        h2 {
            width: 50%;
            font-size: 2.5rem;
        }

        a {
            font-weight: bold;
            text-transform: uppercase;
            color: var(--academy-primary);
        }
    }
}
</style>
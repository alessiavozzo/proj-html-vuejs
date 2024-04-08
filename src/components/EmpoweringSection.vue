<script>
export default {
    name: "EmpoweringSection"
}
</script>


<template>
    <section id="empowering">
        <div class="container">
            <div class="row">
                <!-- img -->
                <div class="image col-6">
                    <img src="/img/h5-img-2.jpg" alt="students-looking-up">
                </div>

                <!-- text -->
                <div class="text d-flex col-6">
                    <h2>Empowering Children to Reach Their Potential</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis fugit fugiat voluptatem eum
                        cum
                        minus similique ex natus distinctio est in maxime ipsa dolores ratione quas quis vero, sint quia
                        eius at optio quibusdam officia consequatur. Consequatur ipsam sequi veniam!</p>
                    <div class="counters d-flex">
                        <div class="user-stories d-flex col-6">
                            <div class="number">168</div>
                            <span>User Stories</span>
                        </div>
                        <div class="events d-flex col-6">
                            <div class="number">347</div>
                            <span>Events</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

</template>


<style scoped>
#empowering {
    padding: 3rem 0;

    .text {
        flex-direction: column;
        padding: 1.5rem;
        gap: 1rem;

        h2 {
            font-size: 2.5rem;
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
                font-size: 3rem;
            }

            span {
                font-size: 1.5rem;
            }
        }
    }
}
</style>
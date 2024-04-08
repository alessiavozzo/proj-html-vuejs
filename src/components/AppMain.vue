<script>
export default {
    name: "AppMain"
}
</script>

<template>
    <main id="site_main">

        <section id="subjects">
            <div class="container">
                <div class="row">
                    <div class="card d-flex col-2">
                        <img src="/img/h5-custom-icon-1.png" alt="subject-icon">
                        <h3>Languages</h3>
                    </div>

                </div>
            </div>
        </section>

    </main>
</template>


<style scoped>
.card {
    border: 1px solid black;
    padding: 1rem;
    align-items: center;
    flex-direction: column;
    gap: 1.5rem;
    background-color: var(--academy-subject);
}
</style>
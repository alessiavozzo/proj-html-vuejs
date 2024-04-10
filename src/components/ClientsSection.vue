<script>
import { clients } from '../assets/js/clients';

export default {
    name: "ClientsSection",
    data() {
        return {
            clients: clients,
        }
    }
}
</script>


<template>
    <section id="clients">
        <div class="container">
            <div class="row">
                <div class="client col-3" v-for="client in clients" @mouseenter="client.onHover = true"
                    @mouseleave="client.onHover = false">
                    <img :src="client.onHover === true ? `/img/${client.hoverImage}` : `/img/${client.image}`" alt="">
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped>
#clients {
    padding: 5.5rem 0;

    img {
        width: 100%;
    }
}
</style>
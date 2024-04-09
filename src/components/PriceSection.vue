<script>
import { pricePlansData } from '../assets/js/price-plans';

export default {
    name: "PriceSection",

    data() {
        return {
            pricePlansData: pricePlansData
        }
    },
    methods: {
        //had to modify price-plans.js
        //replace the blank space in plansOptions elements with '_' (to get plan data in position option-name)
        getRowData(plan, option) {
            return plan[option.toLowerCase().replace(/\s/g, '_')]
        }
    }



}
</script>


<template>
    <section id="prices">
        <div class="container">

            <!-- table -->
            <table class="table">
                <!-- thead -->
                <thead>
                    <tr>
                        <th>#</th>
                        <th v-for="plan in pricePlansData.pricePlans">
                            <img :src="`/img/${plan.image}`" alt="">
                            <div class="plan">{{ plan.plan }}</div>
                            <div class="price">{{ plan.price }}</div>
                        </th>
                    </tr>
                </thead>
                <!-- tbody -->
                <tbody>
                    <tr v-for="option in pricePlansData.plansOptions" :key="option">
                        <th>{{ option }}</th>
                        <td v-for="plan in pricePlansData.pricePlans">
                            {{ getRowData(plan, option) }}
                        </td>
                    </tr>
                </tbody>
            </table>

        </div>
    </section>
</template>


<style scoped>
#prices {
    background-image: url(/img/background-pattern.jpg);
    padding: 4rem 0;

}
</style>
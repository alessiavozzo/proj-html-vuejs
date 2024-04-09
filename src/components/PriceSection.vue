<script>
import { pricePlansData } from '../assets/js/price-plans';

export default {
    name: "PriceSection",

    data() {
        return {
            pricePlansData: pricePlansData,
            currentClick: null
        }
    },
    methods: {
        //had to modify price-plans.js
        //replace the blank space in plansOptions elements with '_' (to get plan data in position option-name)
        getRowData(plan, option) {
            return plan[option.toLowerCase().replace(/\s/g, '_')]
        },
        changeOption(index) {
            this.currentClick = index
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
                        <th>Save up to 40% by paying weekly</th>
                        <th v-for="(plan, index) in pricePlansData.pricePlans" @click="changeOption(index)"
                            :class="{ active: currentClick === index }">
                            <img :src="`/img/${plan.image}`" alt="">
                            <div class="plan">{{ plan.plan }}</div>
                            <div class="price">{{ plan.price }}</div>
                        </th>
                    </tr>
                </thead>

                <!-- tbody -->
                <tbody>
                    <tr v-for="option in pricePlansData.plansOptions" :key="option">
                        <!-- left options -->
                        <th>{{ option }}</th>
                        <!-- right -->
                        <td v-for="plan in pricePlansData.pricePlans">
                            <span v-if="getRowData(plan, option) === true">
                                <i class="fa-solid fa-check" style="color: var(--academy-primary);"></i>
                            </span>
                            <span v-else-if="getRowData(plan, option) === false">
                                <i class="fa-solid fa-xmark"></i>
                            </span>
                            <span v-else>{{ getRowData(plan, option) }}</span>
                        </td>
                    </tr>

                    <tr>
                        <th></th>
                        <td v-for="(n, nIndex) in 3">
                            <a href="#" class="btn" :class="{ 'activeBtn': currentClick === nIndex }">Get it now</a>
                        </td>
                    </tr>



                </tbody>
            </table>

        </div>
    </section>
</template>


<style scoped>
#prices {
    background-image: url(/img/page-background-img.png);
    padding: 4rem 0;

    th,
    td {
        border: 1px solid black;
        border-collapse: collapse;
        background-color: var(--academy-lighter);
    }

    table {
        margin: 0 auto;
        width: 100%;
        border-collapse: collapse;

        thead th {
            padding: 1.5rem;
            line-height: 1.5rem;
            width: calc(100% / 4);

            &:not(:first-of-type) {
                background-color: var(--academy-subject);
            }

            &.active {
                border-top: 5px solid var(--academy-primary);
            }
        }

        tbody {

            th,
            td {
                padding: 1.5rem;
            }

            th {
                text-align: left;
            }

            tr:last-of-type {
                >th {
                    background-color: transparent;
                    border: none;
                }

                >td {
                    background-color: var(--academy-subject);

                    .btn {
                        border: 1px solid black;
                        background-color: var(--academy-lighter);

                        &.activeBtn {
                            background-color: var(--academy-primary);
                            color: var(--academy-lighter);
                        }
                    }
                }
            }


            td {
                text-align: center;
            }
        }
    }

}
</style>
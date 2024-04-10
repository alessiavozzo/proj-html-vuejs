<script>
import { pricePlansData } from '../../assets/js/price-plans';

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

            <!-- intro -->
            <div class="intro">
                <h2>Pricing Plans</h2>
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus dolorum placeat illum illo.</p>
            </div>

            <!-- table -->
            <div class="table-container">
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
                                <a href="#" class="btn" target="_blank"
                                    :class="{ 'activeBtn': currentClick === nIndex }">Get it now</a>
                            </td>
                        </tr>



                    </tbody>
                </table>

                <!-- buttons -->
                <div class="buttons d-flex">
                    <img class="mikado" src="/svg/svg-0.svg" alt="">
                    <img class="cart" src="/svg/svg-2.svg" alt="">
                </div>
            </div>


        </div>
    </section>
</template>


<style scoped>
#prices {
    background-image: url(/img/background-pattern.jpg);
    background-position-y: 180%;
    padding: 4rem 0 8rem 0;
    border-bottom: 1px solid var(--border-elements);

    .intro {
        text-align: center;
        padding: 3rem 0 6rem 0;

        h2 {
            padding-bottom: 0.5rem;
            font-size: 3.5rem;
            font-weight: 600;
        }

        p {
            font-size: 1.3rem;
        }
    }

    .table-container {
        padding: 1rem;
        position: relative;

        th,
        td {
            border: 1px solid var(--border-elements);
            background-color: var(--academy-lighter);
        }

        table {
            margin: 0 auto;
            width: 100%;
            border-collapse: collapse;

            thead th {
                padding: 2.5rem 1.5rem;
                line-height: 1.5rem;
                width: calc(100% / 4);
                border-top: 5px solid var(--border-top-table);
                font-size: 1.8rem;
                font-weight: 600;

                &:not(:first-of-type) {
                    background-color: var(--academy-subject);

                    >img,
                    .plan,
                    .price {
                        padding-bottom: 1rem;
                    }
                }

                &:first-of-type {
                    text-align: left;
                    vertical-align: bottom;
                    line-height: 2rem;
                }

                &.active {
                    border-top: 5px solid var(--academy-primary);
                }
            }

            tbody {
                font-size: 1.3rem;
                color: var(--text-dark);

                th,
                td {
                    padding: 1rem;
                }

                th {
                    text-align: left;
                }

                td {
                    text-align: center;
                    font-size: 1.6rem;
                }

                tr:last-of-type {
                    >th {
                        background-color: transparent;
                        border: none;
                    }

                    >td {
                        background-color: var(--academy-subject);
                        padding: 1.8rem 0;

                        .btn {
                            border: 1px solid var(--border-elements);
                            background-color: var(--academy-lighter);
                            color: var(--text-dark);
                            font-size: 1.1rem;
                            font-weight: 600;
                            padding: 1rem 2rem;

                            &:hover {
                                background-color: var(--academy-primary);
                                color: var(--academy-lighter);
                            }

                            &.activeBtn {
                                background-color: var(--academy-primary);
                                color: var(--academy-lighter);
                                border-color: var(--academy-primary);
                            }
                        }
                    }
                }


            }
        }
    }

    .buttons {
        flex-direction: column;
        gap: 0.5rem;
        align-items: center;
        justify-content: center;
        position: absolute;
        right: -1.8em;
        top: 3rem;

        img {
            height: 50px;
            width: 50px;
            cursor: pointer;

            &.mikado {
                padding: 0.5rem;
                background-color: var(--fill-logo);
            }

            &.cart {
                background-color: var(--academy-lighter);
                padding: 0.9rem;
                box-shadow: 0 0 2px 1px var(--border-elements);
            }
        }
    }

}
</style>
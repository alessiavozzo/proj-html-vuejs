<script>

export default {
    name: "AppFooter",
    props: {
        footerCols: Array,
        icons: Object
    }
}
</script>

<template>
    <footer id="site_footer">
        <div class="container">

            <!-- footer top -->
            <div class="top-footer">
                <div class="row">

                    <div class="footer-column col-3 d-flex" v-for="col in footerCols">
                        <!-- title -->
                        <h3 v-if="col.title">{{ col.title }}</h3>

                        <!-- first col -->
                        <div class="info-contacts d-flex"
                            v-if="col.logo && col.text && col.contacts && col.availability">
                            <img :src="`/img/${col.logo}`" alt="">
                            <div class="text">{{ col.text }}</div>
                            <div class="contacts">{{ col.contacts }}</div>
                            <div class="availability">{{ col.availability }}</div>
                        </div>

                        <!-- other cols -->
                        <ul v-if="col.links">
                            <li v-for="link in col.links">
                                <a :href="link.href" :class="{ bold: link.name }">{{ link.name || link.text }}</a>
                                <div v-if="link.author">{{ link.author }}</div>
                            </li>
                        </ul>
                        <div class="map" v-if="col.image">
                            <img :src="`/img/${col.image}`" alt="">
                        </div>
                    </div>


                </div>

            </div>

            <!-- footer-bottom -->
            <div class="bottom-footer d-flex">
                <div class="copyright">Copyrights 2017 &copy; Mikado Themes</div>
                <div class="socials d-flex">
                    <div class="call">CALL +44 300 303 0266</div>
                    <div class="follow">FOLLOW US</div>
                    <div class="social-links d-flex">
                        <a v-for="icon in icons.socialIcons" :href="icon.href" target="_blank">
                            <i :class="icon.iconClass"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <a class="go-up-btn" href="#site_header">
            <i class="fa-solid fa-chevron-up"></i>
            <span>TOP</span>
        </a>
    </footer>
</template>


<style scoped>
#site_footer {
    background-color: var(--academy-footer);
    padding: 8rem 0 0 0;
    color: var(--footer-text);
    position: relative;

    .top-footer {
        padding-bottom: 5rem;
        border-bottom: 1px solid var(--text-dark);

        .footer-column {
            flex-direction: column;
            gap: 1.5rem;

            .info-contacts {
                flex-direction: column;
                justify-content: center;
                align-items: flex-start;
                gap: 2rem;

                img {
                    height: 27px
                }

                .contacts::before {
                    content: "\f095";
                }

                .availability::before {
                    content: "\f017"
                }

                .contacts::before,
                .availability::before {
                    font-family: FontAwesome;
                    padding-right: 0.5rem;
                }
            }

            h3 {
                font-size: 1.8rem;
                color: var(--academy-lighter);
                font-weight: 500;
            }


            ul {
                list-style: none;
                display: flex;
                flex-direction: column;
                gap: 1rem;

                a {
                    color: var(--footer-text);
                    cursor: pointer;

                    &:hover {
                        color: var(--academy-primary);
                    }
                }

                a.bold {
                    font-weight: bold;
                    font-size: 1.3rem;
                }
            }

            .map {
                img {
                    width: 70%;
                }
            }
        }

        .footer-column:last-of-type {
            text-align: center;
        }

        .text,
        li {
            line-height: 1.5rem;
        }
    }

    .bottom-footer {
        padding: 2.5rem 0;
        justify-content: space-between;
        align-items: center;
        color: var(--text-dark);

        .socials,
        .social-links {
            gap: 1.5rem;

            a {
                color: var(--footer-text);

                &:hover {
                    color: var(--academy-primary);
                }
            }
        }
    }

    .go-up-btn {
        width: 60px;
        height: 60px;
        padding: 0.5rem;
        background-color: var(--academy-primary);
        color: var(--academy-lighter);
        display: flex;
        flex-direction: column;
        gap: 0.1rem;
        justify-content: center;
        align-items: center;
        font-size: 1rem;
        position: absolute;
        right: 0;
        bottom: 0;
    }

}
</style>
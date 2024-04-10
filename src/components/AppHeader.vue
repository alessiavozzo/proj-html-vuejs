<script>
export default {
    name: "AppHeader",
    data() {
        return {
            imgPath: "/img/",
            bgImages: [
                "h5-slide-1-background.jpg",
                "h5-slide-2-background.jpg",
                "h5-slide-3-background.jpg",
            ],
            counter: 0,
            cartItems: 0
        }
    },
    props: {
        navLinks: Array,
        icons: Object
    },
    methods: {
        next() {
            this.counter++
            if (this.counter > this.bgImages.length - 1) {
                this.counter = 0
            }
        },
        prev() {
            this.counter--
            if (this.counter < 0) {
                this.counter = this.bgImages.length - 1
            }
        }
    }
}
</script>

<template>
    <header id="site_header" :style="{ 'background-image': `url('${imgPath}${bgImages[counter]}')` }">
        <div class="controls d-flex">
            <button type="button" class="prev-btn" @click="prev()">
                <i class="fa-solid fa-chevron-left"></i>
            </button>
            <button type="button" class="next-btn" @click="next()">
                <i class="fa-solid fa-chevron-right"></i>
            </button>
        </div>

        <div class="container">

            <!-- top header with logo + nav-links -->
            <nav class="top-header d-flex">

                <!-- left: logo -->
                <div class="logo">
                    <img src="/img/logo-light.png" alt="iAcademy-logo-white">
                </div>
                <!-- center : links -->
                <div class="nav-links">
                    <ul class="list-inline">
                        <li v-for="navLink in navLinks">
                            <a :href="navLink.href">{{ navLink.link }}</a>
                        </li>
                    </ul>
                </div>

                <!-- right: icons -->
                <div class="nav-icons">
                    <ul class="list-inline">
                        <li v-for="icon in icons.navIcons">
                            <a :href="icon.href"
                                :style="{ 'position': icon.iconClass.includes('fa-bag-shopping') ? 'relative' : 'static' }">
                                <i :class="icon.iconClass"></i>
                                <span class="cart-items" v-if="icon.iconClass.includes('fa-bag-shopping')">{{ cartItems
                                    }}</span>
                            </a>
                        </li>
                    </ul>
                </div>

            </nav>

            <!-- jumbotron -->
            <div class="bottom-jumbo d-flex">
                <h1>Contemporary Ideas</h1>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit cumque dignissimos qui quasi
                    praesentium a, maxime neque adipisci perspiciatis recusandae?</p>
                <a href="#" class="btn">Register now</a>
            </div>

            <div class="thumbnail">
                <i class="fa-solid fa-circle" v-for="(thumb, index) in bgImages.length" @click="counter = index"
                    :class="{ 'active': index === counter }"></i>
            </div>

        </div>


    </header>
</template>


<style scoped>
#site_header {
    /* background-image: url(/img/h5-slide-3-background.jpg); */
    height: 680px;
    background-size: cover;
    background-position: center;
    position: relative;

    nav {
        padding: 1.5rem 0;
        justify-content: space-between;
        align-items: center;

        img {
            height: 30px;
        }

        ul {
            a {
                text-transform: uppercase;
                color: var(--academy-lighter);
            }
        }

        .nav-links ul {
            gap: 2.5rem;
        }

        .nav-icons ul {
            gap: 2rem;
        }

    }

    .cart-items {
        position: absolute;
        top: -0.5rem;
        right: -0.5rem;
        font-size: 0.9rem;
        border-radius: 50%;
        height: 1rem;
        width: 1rem;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: var(--academy-primary);
    }

    .bottom-jumbo {
        flex-direction: column;
        align-items: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        width: 70%;
        gap: 1rem;
        color: var(--academy-lighter);

        h1 {
            font-size: 5rem;
            font-weight: 500;
        }

        p {
            font-size: 1.2rem;
            padding-bottom: 1.5rem;
        }

        .btn {
            color: var(--academy-lighter);
            background-color: var(--academy-primary);
            padding: 1rem 2rem;
        }
    }

    .controls {
        width: 100%;
        justify-content: space-between;
        position: absolute;
        top: 50%;
        padding: 0 3rem;

        .next-btn,
        .prev-btn {
            font-size: 3rem;
            border: none;
            background-color: transparent;
            color: var(--fade-light);
            font-size: 5rem;
        }
    }

    .thumbnail {
        position: absolute;
        width: 100%;
        bottom: 1.5rem;
        left: 0;
        display: flex;
        gap: 0.5rem;
        justify-content: center;

        i {
            color: var(--fade-light);

            &.active {
                color: var(--academy-lighter);
            }
        }
    }
}
</style>
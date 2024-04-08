<script>
export default {
    name: "AppHeader",
    data() {
        return {

        }
    }
}
</script>

<template>
    <header id="site_header">

        <div class="container">

            <!-- top header with logo + nav-links -->
            <nav class="top-header d-flex">
                <!-- left -->
                <div class="logo">
                    <img src="/img/logo-light.png" alt="iAcademy-logo-white">
                </div>
                <!-- center -->
                <div class="nav-links">
                    <ul class="list-inline">
                        <li>
                            <a href="#">Home</a>
                        </li>
                        <li>
                            <a href="#">Courses</a>
                        </li>
                        <li>
                            <a href="#">Instructors</a>
                        </li>
                        <li>
                            <a href="#">Events</a>
                        </li>
                        <li>
                            <a href="#">Pages</a>
                        </li>
                        <li>
                            <a href="#">Elements</a>
                        </li>

                    </ul>
                </div>
                <!-- right -->
                <div class="nav-icons">
                    <ul class="list-inline">
                        <li>
                            <i class="fa-solid fa-magnifying-glass"></i>
                        </li>
                        <li>
                            <i class="fa-solid fa-bag-shopping"></i>
                        </li>
                        <li>
                            <i class="fa-solid fa-bars"></i>
                        </li>
                    </ul>
                </div>

            </nav>

            <!-- jumbotron -->
            <div class="bottom-jumbo">

            </div>

        </div>


    </header>
</template>


<style scoped>
#site_header {
    background-image: url(/img/h5-slide-3-background.jpg);
    height: 680px;
    background-size: cover;
    background-position: center;

    nav {
        height: 100px;
        justify-content: space-between;

        img {
            height: 30px;
        }

        ul {
            gap: 1rem;
        }

    }
}
</style>
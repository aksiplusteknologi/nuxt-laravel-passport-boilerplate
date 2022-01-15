<template>
    <div>
        <!-- sidebar  -->
        <nav class="sidebar dark_sidebar">
            <div class="logo d-flex justify-content-between">
                <a class="large_logo" href="/">
                    <img src="/img/logo-aksiplus.png" alt />
                </a>
                <a class="small_logo" href="/index-2.html">
                    <img src="/img/mini_logo.png" alt />
                </a>
                <div class="sidebar_close_icon d-lg-none">
                    <i class="ti-close"></i>
                </div>
            </div>
            <ul id="sidebar_menu">
                <li class>
                    <a href="/#" aria-expanded="false">
                        <div class="nav_icon_small">
                            <img src="/img/menu-icon/1.svg" alt />
                        </div>
                        <div class="nav_title">
                            <span>Dashboard</span>
                        </div>
                    </a>
                </li>

                <li class>
                    <a class="has-arrow" href="/#" aria-expanded="false">
                        <div class="nav_icon_small">
                            <img src="/img/menu-icon/8.svg" alt />
                        </div>
                        <div class="nav_title">
                            <span>Apps</span>
                        </div>
                    </a>
                    <ul>
                        <li>
                            <a href="#">Editor</a>
                        </li>
                        <li>
                            <a href="#">Invoice</a>
                        </li>
                    </ul>
                </li>
            </ul>
        </nav>
        <!--/ sidebar  -->
    </div>
</template>

<script>
export default {};
</script>

<style>
</style>
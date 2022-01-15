<template>
    <section class="main_content dashboard_part large_header_bg">
        <!-- menu  -->
        <Sidebar />

        <!-- Navbar here -->
        <Navbar />

        <!--/ menu  -->
        <div class="main_content_iner overly_inner">
            <div class="container-fluid p-0">
                <!-- page title  -->
                <Nuxt />
            </div>
        </div>

        <!-- footer part -->
    </section>
    <!-- main content part end -->
</template>

<script>
import Navbar from "~~/layouts/partials/Navbar";
import Sidebar from "~~/layouts/partials/Sidebar";

export default {
    components: {
        Navbar,
        Sidebar,
    },
};
</script>

<style>
</style>
<template>
    <div class="container-fluid no-gutters">
        <div class="row" v-if="isLoggedIn">
            <div class="col-lg-12 p-0">
                <div class="header_iner d-flex justify-content-between align-items-center">
                    <div class="sidebar_icon d-lg-none">
                        <i class="ti-menu"></i>
                    </div>
                    <div class="line_icon open_miniSide d-none d-lg-block">
                        <img src="/img/line_img.png" alt />
                    </div>
                    <div class="header_right d-flex justify-content-between align-items-center">
                        <div class="header_notification_warp d-flex align-items-center">
                            <li>
                                <a class="bell_notification_clicker nav-link-notify" href>
                                    <img src="/img/icon/bell.svg" alt />
                                    <!-- <span>2</span> -->
                                </a>
                                <!-- Menu_NOtification_Wrap  -->
                                <div class="Menu_NOtification_Wrap">
                                    <div class="notification_Header">
                                        <h4>Notifications</h4>
                                    </div>
                                    <div class="Notification_body">
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/2.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>Cool Marketing</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/4.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>Awesome packages</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/3.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>what a packages</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/2.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>Cool Marketing</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/4.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>Awesome packages</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                        <!-- single_notify  -->
                                        <div class="single_notify d-flex align-items-center">
                                            <div class="notify_thumb">
                                                <a href>
                                                    <img src="/img/staf/3.png" alt />
                                                </a>
                                            </div>
                                            <div class="notify_content">
                                                <a href>
                                                    <h5>what a packages</h5>
                                                </a>
                                                <p>Lorem ipsum dolor sit amet</p>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="nofity_footer">
                                        <div class="submit_button text-center pt_20">
                                            <a href class="btn_1 green">See More</a>
                                        </div>
                                    </div>
                                </div>
                                <!--/ Menu_NOtification_Wrap  -->
                            </li>
                        </div>
                        <div class="profile_info d-flex align-items-center">
                            <div class="profile_thumb mr_20">
                                <img :src="user.avatar" alt="#" />
                            </div>
                            <div class="author_name">
                                <h4 class="f_s_15 f_w_500 mb-0">{{ user.name }}</h4>
                                <p
                                    class="f_s_12 f_w_400"
                                >{{ user.username ? user.username : user.email }}</p>
                            </div>
                            <div class="profile_info_iner">
                                <div class="profile_info_details">
                                    <NuxtLink to="/profile">My Profile</NuxtLink>
                                    <a @click="logout">Log Out</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
    name: "app-navbar",

    computed: {
        ...mapGetters(["user", "isLoggedIn"]),
    },
    methods: {
        async logout() {
            await this.$auth.logout().then(() => {
                localStorage.removeItem("auth._token.local");

                setTimeout(() => {
                    location.reload();
                }, 1000);
            });
        },
    },
};
</script>

<style>
</style>
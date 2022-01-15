<template>
    <section class="ftco-section">
        <div class="container">
            <div class="row justify-content-center">
                <div class="col-md-7 col-lg-5">
                    <div class="wrap">
                        <div
                            class="img"
                            style="background-image:url(https://valueconsulttraining.com/wp-content/uploads/2015/08/Project-Management1.jpg)"
                        ></div>
                        <div class="login-wrap p-4">
                            <div class="d-flex">
                                <div class="w-100">
                                    <h3 class="mb-2">Sign In</h3>
                                </div>
                                <div class="w-100">
                                    <p class="social-media d-flex justify-content-end">
                                        <a
                                            href="#"
                                            class="social-icon d-flex align-items-center justify-content-center"
                                        >
                                            <span class="fa fa-facebook"></span>
                                        </a>
                                        <a
                                            href="#"
                                            class="social-icon d-flex align-items-center justify-content-center"
                                        >
                                            <span class="fa fa-twitter"></span>
                                        </a>
                                    </p>
                                </div>
                            </div>
                            <form @submit.prevent="doLogin" class="signin-form">
                                <div class="form-group mt-3">
                                    <input
                                        v-model="form.username"
                                        type="text"
                                        class="form-control"
                                        placeholder="Input Your Username"
                                    />
                                </div>
                                <div class="form-group">
                                    <input
                                        v-model="form.password"
                                        id="password-field"
                                        type="password"
                                        class="form-control"
                                        placeholder="Input Your Password"
                                    />
                                </div>
                                <div class="form-group">
                                    <button
                                        type="submit"
                                        class="form-control btn btn-primary rounded submit px-3"
                                    >Sign In</button>
                                </div>
                                <div class="form-group d-md-flex">
                                    <div class="w-50 text-left">
                                        <a href="#">Forgot Password</a>
                                    </div>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    layout: "auth",

    data: () => ({
        form: {
            username: "",
            password: "",
        },
    }),

    computed: {
        isLoggedIn: function () {
            return this.$store.getters.isLoggedIn;
        },
    },

    mounted() {
        // if(this.isLoggedIn) {
        //     window.location = '/'
        // }
    },

    methods: {
        async doLogin() {
            if (this.form.username == "") {
                alert("Username can't be empty");
            } else if (this.form.password == "") {
                alert("Password can't be empty");
            } else {
                try {
                    let response = await this.$auth.loginWith("local", {
                        data: this.form,
                    });
                    console.log(response);

                    this.$router.push("/");
                } catch (e) {
                    this.errors = e.response.data.errors;
                }
            }
        },
    },
};
</script>

<style scoped>
body {
    font-family: "Lato", Arial, sans-serif;
    font-size: 16px;
    line-height: 1.8;
    font-weight: normal;
    color: gray;
    background: #eceff1;
}

.ftco-section {
    padding: 7em 0;
}

.wrap {
    width: 100%;
    overflow: hidden;
    background: #fff;
    border-radius: 5px;
    -webkit-box-shadow: 0 10px 34px -15px rgb(0 0 0 / 24%);
    -moz-box-shadow: 0 10px 34px -15px rgba(0, 0, 0, 0.24);
    box-shadow: 0 10px 34px -15px rgb(0 0 0 / 24%);
}
.wrap .img {
    height: 200px;
}
.img {
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
}
</style>
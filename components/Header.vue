<template>
    <div class="row">
        <div class="col-12">
            <div class="page_title_box d-flex align-items-center justify-content-between">
                <div class="page_title_left">
                    <h3 class="f_s_30 f_w_700 dark_text">{{ title }}</h3>
                    <ol class="breadcrumb page_bradcam mb-0">
                        <li class="breadcrumb-item" v-for="(b, index) in breadcrumb" :key="index">
                            <a v-if="index != breadcrumb.length - 1">{{ b }}</a>
                            <span v-else>{{ b }}</span>
                        </li>
                    </ol>
                </div>
                <slot name="button" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["title", "breadcrumb"],
};
</script>

<style>
</style>
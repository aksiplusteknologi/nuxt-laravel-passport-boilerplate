<template>
    <div>
        <Header title="Dashboard Administrator" :breadcrumb="['Home', 'Dashboard']">
            <template v-slot:button>
                <button class="btn btn-primary">Create Report</button>
            </template>
        </Header>
    </div>
</template>

<script>
export default {
    name: "IndexPage",

    methods: {},
};
</script>

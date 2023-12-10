<script setup>
import { reactive, toRefs } from "vue";
import { Head, Link, router } from "@inertiajs/vue3";
import MainLayout from "@/Layouts/MainLayout.vue";

let data = reactive({ post: null });
const form = reactive({ file: null });

const props = defineProps({ postByUser: Object, user: Object });
const { postByUser, user } = toRefs;
</script>

<template>
    <!-- why is head not working? hmmm -->
    <Head title="USER" />
    <MainLayout>
        <div class="bg-red-500">user.Vue</div>
    </MainLayout>
</template>

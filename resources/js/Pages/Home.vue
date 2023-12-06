<script setup>
import { Head } from "@inertiajs/vue3";
import MainLayout from "@/Layouts/MainLayout.vue";
</script>

<template>
    <!-- why is head not working? hmmm -->
    <Head title="HOME" />
    <MainLayout>
        <div class="bg-green-500">Home.Vue</div>
    </MainLayout>
</template>

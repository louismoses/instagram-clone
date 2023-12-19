<script setup>
import { ref, onMounted, toRefs } from "vue";
import { Head, Link, router } from "@inertiajs/vue3";
import MainLayout from "@/Layouts/MainLayout.vue";

import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation } from "vue3-carousel";
</script>

<template>
    <!-- why is head not working? hmmm -->
    <Head title="HOME" />
    <MainLayout>
        <div class="bg-green-500">Home.Vue</div>
    </MainLayout>
</template>

<template>
    <h3>Index View</h3>
    Message: {{ message }} <br />
    Data: {{ data }} <br />
    Name: {{ data.name }} <br />
    This page alive since {{ timer }}
    <Link href="/hello">Show Page</Link>
</template>

<script setup>
import { Link } from '@inertiajs/inertia-vue3'
import { ref } from 'vue'

const timer = ref(0);
defineProps(['message', 'data']);

setInterval(() => {
    timer.value++;
}, 1000);

</script>
<!-- This can be use for specific layout -->
<!-- <script>
import MainLayout from '../Layouts/MainLayout.vue'
export default {
    layout: MainLayout
}
</script> -->

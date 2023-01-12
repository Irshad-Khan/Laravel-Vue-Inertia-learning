<template>
    <div>
        <h3>Index View</h3>
        Message: {{ message }} <br />
        Data: {{ data }} <br />
        Name: {{ data.name }} <br />
        <Link href="/hello">Show Page</Link>
    </div>
</template>

<script setup>
import { Link } from '@inertiajs/inertia-vue3'
defineProps(['message','data']);
</script>

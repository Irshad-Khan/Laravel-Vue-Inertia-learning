<template>
  <div>
    <Link href="/">Index Page</Link>&nbsp;
    <Link href="/hello">Show Page</Link>&nbsp;
    <Link :href="route('listings.index')">Listings</Link>
    <div v-if="flashSuccess" class="success">
      {{ flashSuccess }}
    </div>
    <slot />
  </div>
</template>

<script setup>
import {computed} from 'vue'
import { Link, usePage } from '@inertiajs/inertia-vue3'
const page = usePage()
const flashSuccess = computed(() => page.props.value.flash.success)
</script>

<style scoped>
.success{
    background-color: green;
    color: white;
}
.error{
    color: red;
}
</style>

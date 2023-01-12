<template>
  <div>
    <Link href="/">Index Page</Link>&nbsp;
    <Link href="/hello">Show Page</Link>
    <slot />
  </div>
</template>

<script setup>
import { Link } from '@inertiajs/inertia-vue3'
</script>

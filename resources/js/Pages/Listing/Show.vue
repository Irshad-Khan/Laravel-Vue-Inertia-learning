<template>
  <h3>Listing Detal</h3>
  <ListingAddress :listing="listing" />
</template>

<script setup>
import ListingAddress from '@/Components/ListingAddress.vue'
defineProps({
  listing: Object,
})
</script>

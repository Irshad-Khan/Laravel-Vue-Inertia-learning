<template>
  <h3>Listing <Link href="/listings/create">Create</Link></h3>
  <div v-for="listing in listings" :key="listing.id">
    <div>
      <Link :href="route('listings.show', { listing: listing.id })">
        <ListingAddress :listing="listing" />
      </Link>
    </div>
    <div>
      <Link :href="route('listings.edit', { listing: listing.id })">Edit</Link>
    </div>
    <div>
      <Link :href="route('listings.destroy', { listing: listing.id })" method="DELETE">Delete</Link>
    </div>
  </div>
</template>

<script setup>
import { Link } from '@inertiajs/inertia-vue3'
import ListingAddress from '@/Components/ListingAddress.vue'
defineProps({
  listings: Array,
})
</script>

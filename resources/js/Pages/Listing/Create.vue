<template>
  <h3>Create Listing</h3>
  <form @submit.prevent="create">
    <p>
      <label for="beds">Beds</label>
      <input id="beds" v-model.number="form.beds" type="text" name="beds" />
    </p><div v-if="form.errors.beds" class="error">{{ form.errors.beds }}</div>

    <p>
      <label for="baths">Baths</label>
      <input id="baths" v-model.number="form.baths" type="text" name="baths" />
    </p><div v-if="form.errors.baths" class="error">{{ form.errors.baths }}</div>
    <p>
      <label for="area">Area</label>
      <input id="area" v-model.number="form.area" type="text" name="area" />
    </p><div v-if="form.errors.area" class="error">{{ form.errors.area }}</div>
    <p>
      <label for="city">City</label>
      <input id="city" v-model="form.city" type="text" name="city" />
    </p><div v-if="form.errors.city" class="error">{{ form.errors.city }}</div>
    <p>
      <label for="street">Street</label>
      <input id="street" v-model="form.street" type="text" name="street" />
    </p><div v-if="form.errors.street" class="error">{{ form.errors.street }}</div>
    <p>
      <label for="street_nr">Street Number</label>
      <input id="street_nr" v-model="form.street_nr" type="text" name="street_nr" />
    </p><div v-if="form.errors.street_nr" class="error">{{ form.errors.street_nr }}</div>
    <p>
      <label for="code">Postal Code</label>
      <input id="code" v-model="form.code" type="text" name="code" />
    </p><div v-if="form.errors.code" class="error">{{ form.errors.code }}</div>
    <p>
      <label for="price">Price</label>
      <input id="price" v-model.number="form.price" type="text" name="price" />
    </p><div v-if="form.errors.price" class="error">{{ form.errors.price }}</div>
    <p>
      <button id="submit" type="submit" name="submit">Create</button>
    </p>
  </form>
</template>

<script setup>
// import { reactive } from 'vue'
// import { Inertia } from '@inertiajs/inertia'

import {useForm} from '@inertiajs/inertia-vue3'

const form = useForm({
  beds: 0,
  baths: 0,
  area: 0,
  city: null,
  street: null,
  street_nr: null,
  code: null,
  price: 0,
})

const create = () => form.post(route('listings.store'))
</script>

<style scoped>
label{
    margin-right: 2em;
}
p{
    padding: 2px;
}
</style>

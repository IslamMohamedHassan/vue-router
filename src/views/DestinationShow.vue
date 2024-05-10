<template>
   <section v-if="destination" class="destination">
    <h1>{{destination.name}}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name">
      <p>{{destination.description}}</p>
    </div>
  </section>
</template>

<script setup>
import { ref, watch } from 'vue';
import { useRoute } from 'vue-router';

const destination = ref(null);
const route = useRoute();

const props =  defineProps({
    id: String,
    slug: String
})



async function fetchDestination(){
    const res = await fetch(
    `https://travel-dummy-api.netlify.app/${props.slug}.json`
  );
  destination.value = await res.json()
}

fetchDestination()

watch(()=> route.params, fetchDestination)

</script>

<style>

</style>

<script setup>
import sourceData from "@/data.json";
import { ref } from "vue";
import { RouterLink } from "vue-router";

const countryData = ref(sourceData);
console.log(countryData.value);  

</script>

<template>
    <div id="nav">
        <router-link to="/">Home</router-link>
        <router-link v-for="item in countryData.destinations" :key="item.id"
            :to="{ name: 'destination', params: { id: item.id ,slug:item.slug}}">
               {{ item.name }}
        </router-link>
    </div>
</template>



<style></style>
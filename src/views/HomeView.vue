<script setup>
import sourceData from "@/data.json";
import { ref } from "vue";
import { RouterLink } from "vue-router";


const countryData = ref(sourceData);

console.log(countryData.value);  
</script>

<template>
     <div class="home">
          <h1>All Destinations</h1>
          <div class="destinations">
               <router-link v-for="item in countryData.destinations" :key="item.id" :to="{name: 'destination' ,  params:{id: item.id, slug:item.slug}}">
                    <h2>{{ item.name }}</h2>
                    <img :src="`/images/${item.image}`" :alt="item.name" />
               </router-link>
            
          </div>
     </div>

</template>

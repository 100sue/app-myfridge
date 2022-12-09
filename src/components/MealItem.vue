<template>
    <div
      class="bg-gray-400  shadow rounded-xl hover:scale-105 transition-all"
    >
      <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
        <img
          :src="meal.strMealThumb"
          :alt="meal.strMeal"
          class="rounded-t-xl w-full h-48 object-cover"
        />
      </router-link>
      <div class="p-3">
        <h3 class="font-bold text-lg text-orange-600 mb-2">{{ meal.strMeal }}</h3>
        <p class="mb-4">
          {{ $filters.truncateWords(meal.strInstructions, 20) }}
        </p>
        <h4 class="text-white mt-5 flex items-center justify-center hover:text-orange-600 transition-colors ">- To see the recipe click on the picture -</h4>
        <h5 class="mt-4 flex items-center justify-center ">Or, see the recipe on Video :</h5>
        <div class="flex items-center justify-center mt-4 mb-3">
          <YouTubeButton :href="meal.strYoutube" />
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import YouTubeButton from './YouTubeButton.vue';
  
  const { meal } = defineProps({
    meal: {
      required: true,
      type: Object
    }
  })
  
  </script>
  
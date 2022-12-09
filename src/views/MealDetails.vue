<template>
    <div class="max-w-[800px] mx-auto p-8">
      <h1 class="text-4xl font-bold mb-5 text-orange-500">{{ meal.strMeal }}</h1>
      <img :src="meal.strMealThumb" :alt="meal.strMeal" class="max-w-[100%] rounded-t-2xl">
      <div class="flex items-center justify-center gap-12 mt-2">
        <div>
          <strong class="font-bold text-orange-600">Category:</strong> {{ meal.strCategory }}
        </div>
        <div>
          <strong class="font-bold text-orange-600">Area:</strong> {{ meal.strArea }}
        </div>
        <div>
          <strong class="font-bold text-orange-600">Tags:</strong> {{ meal.strTags }}
        </div>
      </div>
  
      <div class="my-3">
        {{ meal.strInstructions }}
      </div>
  
      <div class="flex items-center justify-center gap-20">
        <div>
          <h2 class="text-2xl font-semibold mb-2">Ingredients:</h2>
          <ul>
            <template v-for="(el, ind) of new Array(20)">
              <li v-if="meal[`strIngredient${ind + 1}`]">
              {{ ind + 1 }}. {{ meal[`strIngredient${ind + 1}`] }}
              </li>
            </template>
          </ul>
        </div>
        <div>
          <h2 class="text-2xl font-semibold mb-2">Measures:</h2>
          <ul>
            <template v-for="(el, ind) of new Array(20)">
              <li v-if="meal[`strMeasure${ind + 1}`]">
              {{ ind + 1 }}. {{ meal[`strMeasure${ind + 1}`] }}
              </li>
            </template>
          </ul>
        </div>
      </div>
      <div class="mt-10 mb-3 flex items-center justify-center">
          <YouTubeButton :href="meal.strYoutube" />
      </div>
  
  
    </div>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import { useRoute } from 'vue-router';
  import axiosClient from '../axiosClient';
  import YouTubeButton from '../components/YouTubeButton.vue';
  
  const route = useRoute();
  const meal = ref({})
  
  onMounted(() => {
    axiosClient.get(`lookup.php?i=${route.params.id}`)
      .then(({ data }) => {
        meal.value = data.meals[0] || {}
      })
  })
  
  </script>
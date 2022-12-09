<template>
    <header class="bg-white shadow h-16 flex justify-between items-stretch">
      <router-link
        :to="{ name: 'home' }"
        class="inline-flex items-center h-full px-5 text-3xl text-orange-500 font-bold font-serif "
      >
        Like Bocuse
      </router-link>
      <div class="flex items-center gap-1">
        <router-link
          :to="{ name: 'byName' }"
          class="inline-flex items-center px-2 h-full font-semibold transition-colors hover:text-orange-600 "
        >
          Search Meals
        </router-link>
        <router-link
          :to="{ name: 'byLetter' }"
          class="inline-flex items-center px-2 h-full font-semibold transition-colors hover:text-orange-600"
        >
          Meals By Letter
        </router-link>
        <router-link
          :to="{ name: 'ingredients' }"
          class="inline-flex items-center px-2 h-full font-semibold transition-colors hover:text-orange-600"
        >
          Meals By Ingredients
        </router-link>
      </div>
    </header>
  </template>
  
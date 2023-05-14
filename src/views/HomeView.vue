<script setup>
import SearchFilter from '../components/SearchFilter.vue';
import HomeHeading from '../components/HomeHeading.vue';

</script>

<template>
  <div class="min-h-screen px-8 pt-12 pb-10">
    <HomeHeading />

    <div class="flex flex-col">
      <div>
        <SearchFilter v-on:handle-input-change="onInputChange" />
      </div>

      <div class="mt-3" v-if="!searchText">
        <div class="py-1 px-3" v-for="(user, index) in users" :key="index">
          <p class="text-base text-gray-500 dark:text-gray-300">{{ user }}</p>
        </div>
      </div>

      <div class="mt-3" v-if="searchText">
        <span v-if="!searchResult.length" class="px-3 italic text-sm">No result for "{{ searchText }}"</span>

        <span v-if="searchResult.length" class="px-3 text-sm text-emerald-500">
          <strong>{{ searchResult.length }}</strong> results for "{{ searchText }}"
        </span>

        <div class="py-1 px-3" v-for="(user, index) in searchResult" :key="index">
          <p class="text-base text-gray-500 dark:text-gray-300">{{ user }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    users: [
      "Barnabe Guiett",
      "Orland Wolvey",
      "Kikelia MacParland",
      "Cesar Leaming",
      "Dion Bewley",
      "Lana Ottley",
      "Roldan Ovendale",
      "Shayla Payley",
      "Walker Tuffley",
      "Rosella Bockin",
      "Garvey Cassell",
      "Yoko Calton",
      "Jermain Docker",
      "Francklin Escritt",
      "Ashlan Gorges",
      "Janeva Mazin",
      "Sonnie Tunnow",
      "Benji Slora",
      "Antonie Heinzel",
      "Sargent Waszkiewicz",
    ],
    searchText: '',
    searchResult: [],
  }),
  methods: {
    onInputChange(value) {
      this.searchText = value
      this.searchResult = this.users.filter(user => user.toLowerCase().indexOf(value.toLowerCase()) >= 0)
    }
  },
}
</script>
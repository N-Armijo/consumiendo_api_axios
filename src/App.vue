<script setup>
  import {ref, onMounted} from 'vue';
  import axios from 'axios';
  const data = ref ([]);
  const fetchData = async () => {
    try {
      const response = await axios.get('https://randomuser.me/api/?results=200');
      console.log(response);
      data.value = response.data.results;
    } catch (error) {
      console.error(`Error: ${error}`);
    }
  };

  onMounted( () => {
    fetchData();
  });

</script>

<template>
  <div>
    <ul>
      <li v-for="item in data">
        {{ item.name.first }} {{ item.name.last }}
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>

<script setup>
  import {ref, onMounted} from 'vue';
  import axios from 'axios';
  // const data = ref ([]); Ejercicio 1
  //EJERCICIO 2
  // const fecha = ref('');
  // const dolar = ref('');
  // const fechaFormateada = (fecha) => {
  //   const fetchArray = fecha.split('T')[0].split('-');
  //   return `${fetchArray[2]}-${fetchArray[1]}-${fetchArray[0]}`
  // }
  //EJERCICIO 3
  // const ciudad = ref('');
  // const temperatura = ref('');
  //EJERCICIO 4
  // const url = ref('');
  const fetchData = async () => {
    try {
      const response = await axios.get('https://pokeapi.co/api/v2/pokemon/25');
      //EJERCICIO 4
      // const response = await axios.get('https://pokeapi.co/api/v2/pokemon/25');
      // url.value = response.data.sprites.other.home.front_default
      //EJERCICIO 3
      // const response = await axios.get('https://api.gael.cloud/general/public/clima/SCAR');
      // ciudad.value = response.data.Estacion;
      // temperatura.value = response.data.Temp;
      //EJERCICIO 1
      // const response = await axios.get('https://randomuser.me/api/?results=20');  //EJERCICIO 1
      //EJERCICIO 2
      // const response = await axios.get('https://mindicador.cl/api');
      // fecha.value = fechaFormateada(response.data.dolar.fecha);
      // dolar.value = response.data.dolar.valor;

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
    <!-- EJERCICIO 4 -->
    <!-- <h1>Pikachu</h1>
    <img :src="url" alt="pokemon"> -->
    <!-- EJERCICIO 3 -->
    <!-- <h1>En este momento en {{ciudad }} hay {{ temperatura}}°</h1> -->
    <!-- EJERCICIO 2 -->
    <!-- <h1>Valor del dolar el {{ fecha }}</h1>
    <h2>${{ dolar }}</h2> -->
    <!-- EJERCICIO 1 -->
    <!-- <table>
      <tr>
        <th>Nombre Completo</th>
        <th>Direccion</th>
      </tr>
      <tr v-for="item in data">
        <td>
          {{ item.name.first }} {{ item.name.last }}
        </td>
        <td >
          {{ item.location.street.name }} #{{ item.location.street.number }}, {{ item.location.city}}
        </td>
      </tr>
    </table> -->
  </div>
</template>

<style scoped>
  div{
    text-align: center;
  }
</style>

<script setup lang="ts">

import { ref, onMounted } from 'vue'
import Table from './components/Table.vue';

const artData = ref(null);
const art = ref('OC47');
const headers = {
    'login': '493358_stroyzar',
    'pass': 'sAVDkrEbqd',
    'art': art
};

async function getData(headers) {
  const response = await fetch('https://api.forum-auto.ru/v2/listGoods', { headers });
  const data = await response.json();
  console.log(data);
  artData.value = data;
}


</script>


<template>
  <div>
    <form action="" method="get" class="form-example">
      <div class="form-example">
        <label for="articul">Артикул: </label>
        <input type="text" name="articul" id="articul" required v-model="art">
      </div>
      <div class="form-example">
        <input type="submit" value="Get data" @click.prevent="getData">
      </div>
    </form>
    <div class="table" v-if="artData !== null">
      <Table
        :items="artData"
      />
    </div>
  </div>
</template>


<style scoped>

.table{
  margin-top: 20px;
}



</style>

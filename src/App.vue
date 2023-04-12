<script setup>

import { ref, onMounted } from 'vue'
import Table from './components/Table.vue';

const artData = ref(null);
const art = ref('OC47');
const headers = {
    'login': '493358_stroyzar',
    'pass': 'sAVDkrEbqd',
    'art': art,
};
const cors_api_url = 'https://cors-anywhere.herokuapp.com/';

async function getData() {
  const response = await fetch(cors_api_url + 'https://api.forum-auto.ru/v2/listgoods/?' + 
    'login=' + headers.login + '&' +
    'pass=' + headers.pass + '&' +
    'art=' + headers.art.value);
  const data = await response.json();
  console.log(data);
  artData.value = data;
}

// function doCORSRequest(options) {
//   var x = new XMLHttpRequest();
//   x.open(options.method, cors_api_url + options.url);
//   x.onload = x.onerror = function() {
//     console.log(
//       options.method + ' ' + options.url + '\n' +
//       x.status + ' ' + x.statusText + '\n\n' +
//       (x.responseText || '')
//     );
//   };
//   if (/^POST/i.test(options.method)) {
//     x.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
//   }
//   for(let key in options.headers){
//     xhr.setRequestHeader(key, options.headers[key]) 
//   }
//   x.send(options.data);
// }

onMounted(() => {
  // const response = doCORSRequest( { method: 'GET', url: 'https://api.forum-auto.ru/v2/listGoods', headers: headersArt } );
  // console.log(response);
  getData();
})

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

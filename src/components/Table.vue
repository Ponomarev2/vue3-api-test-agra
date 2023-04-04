<script lang="ts" setup>
import type { Header, Item } from "vue3-easy-data-table";

const headers: Header[] = [
  { text: "gid", value: "gid" },
  { text: "brand", value: "brand", sortable: true},
  { text: "art", value: "art"},
  { text: "name", value: "name"},
  { text: "d_deliv", value: "d_deliv", sortable: true},
  { text: "h_deliv", value: "h_deliv", sortable: true},
  { text: "kr", value: "kr", sortable: true},
  { text: "num", value: "num", sortable: true},
  { text: "price", value: "price", sortable: true},
  { text: "whse", value: "whse"},
  { text: "is_returnable", value: "is_returnable", sortable: true},
];

const items: Item[] = [
    {
        "gid": "143431W20",
        "brand": "KNECHT",
        "art": "OC47",
        "name": "Фильтр масляный",
        "d_deliv": 1,
        "h_deliv": 24,
        "kr": 1,
        "num": 50,
        "price": 302,
        "whse": "MSK",
        "is_returnable": 1
    },
    {
        "gid": "29698852S55973747157W308972",
        "brand": "MAHLE",
        "art": "OC47",
        "name": "Фильтр масляный",
        "d_deliv": 3,
        "h_deliv": 51,
        "kr": 1,
        "num": 50,
        "price": 290.2,
        "whse": "MSK-CD",
        "is_returnable": 0
    },
    {
        "gid": "29698852S55977110947W308972",
        "brand": "MAHLE",
        "art": "OC47",
        "name": "Фильтр масляный",
        "d_deliv": 3,
        "h_deliv": 51,
        "kr": 1,
        "num": 50,
        "price": 365.5,
        "whse": "MSK-CD",
        "is_returnable": 1
    },
    {
        "gid": "29698852S55974577747W308972",
        "brand": "MAHLE",
        "art": "OC47",
        "name": "Фильтр масляный",
        "d_deliv": 1,
        "h_deliv": 24,
        "kr": 1,
        "num": 10,
        "price": 1533.1,
        "whse": "MSK-CD",
        "is_returnable": 0
    },
    {
        "gid": "29698852S55977779081W308972",
        "brand": "MAHLE",
        "art": "OC47",
        "name": "Фильтр масляный",
        "d_deliv": 4,
        "h_deliv": 75,
        "kr": 1,
        "num": 50,
        "price": 373.8,
        "whse": "MSK-CD",
        "is_returnable": 1
    },
    {
        "gid": "1194701S55949475567W308972",
        "brand": "KNECHT",
        "art": "OC47",
        "name": "Масляный фильтр",
        "d_deliv": 8,
        "h_deliv": 171,
        "kr": 1,
        "num": 16,
        "price": 349.8,
        "whse": "MSK-CD",
        "is_returnable": 0
    },
    {
        "gid": "1194701S55974063233W308972",
        "brand": "KNECHT",
        "art": "OC47",
        "name": "Масляный фильтр",
        "d_deliv": 1,
        "h_deliv": 24,
        "kr": 1,
        "num": 1,
        "price": 365.5,
        "whse": "MSK-CD",
        "is_returnable": 0
    }
];
</script>


<template>
  <EasyDataTable
    :headers="headers"
    :items="items"
  />
</template>


<style>


</style>
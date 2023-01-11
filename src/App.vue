<script setup>
import TableCard from './components/Table.vue';
import { ref } from "vue";
const labelHeaderConfirmation = ref([
  {
    label: "Template Name",
    val: "templateName",
  },
  {
    label: "Time To Do",
    val: "timeToDo",
  },
  {
    label: "Set Number",
    val: "setNumber",
  },
  {
    label: "Repeat Number",
    val: "repeatNumber",
  },
]);
const dataTableConfirmation = ref([
  {
    templateName: "AlrJvd",
    timeToDo: "14 min",
    repeatNumber: "4",
    id:1
  },
]);
</script>

<template>
  <TableCard
      :header-label-title="labelHeaderConfirmation"
      :data-table="dataTableConfirmation"
  >
    <template #templateName="{ row: customer }">
      <span>{{ customer.id }}. {{ customer.templateName }}</span>
    </template>
    <template #timeToDo="{ row: customer }">
      <span>{{ customer.timeToDo }}</span>
    </template>
    <template #setNumber="{ row: customer }">
      <span>{{ customer.timeToDo }}</span>
    </template>
    <template #repeatNumber="{ row: customer }">
      <span>{{ customer.repeatNumber }}</span>
    </template>
  </TableCard>
</template>

<style scoped lang="scss"></style>

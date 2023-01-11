<script setup>
import { defineProps } from "vue";
defineProps({
  headerLabelTitle: [],
  dataTable: [],
});
</script>

<template>
  <div class="w-full w-full px-3 mx-auto">
    <div
        class="relative flex flex-col min-w-0 break-words w-full mb-2 shadow-lg rounded-3xl bg-white pb-5"
    >
      <div class="header-table"><slot /></div>
      <div class="block w-full overflow-x-auto">
        <table class="items-center w-full border-collapse text-blueGray-700">
          <!--begin head table list-->
          <thead class="bg-white">
          <th
              v-for="(item, index) in headerLabelTitle"
              :key="index"
              class="px-6 text-gray-700 align-middle border border-solid border-blueGray-100 py-3 text-md border-l-0 border-r-0 whitespace-nowrap font-bold text-center"
          >
            {{ item.label }}
          </th>
          </thead>
          <!--end head table list-->
          <!--begin list table -->
          <tbody>
          <template v-for="(row, index) in dataTable" :key="index">
            <tr>
              <template
                  v-for="(itemHead, indexItem) in headerLabelTitle"
                  :key="indexItem"
              >
                <td
                    class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-nowrap bg-white border-none font-bold text-gray-500 text-center pb-5"
                >
                  <slot :name="`${itemHead.val}`" :row="row"></slot>
                </td>
              </template>
            </tr>
          </template>
          </tbody>
          <!--end list table-->
        </table>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
table {
  margin: 0 auto;
  width: 100%;
}
thead th {
  background-color: #f2f7f8;
  border: unset;
}
thead th:first-child {
  width: 15%;
  padding: 0 !important;
  border-radius: 100px 0 0 100px;
}
thead th:last-child {
  border-radius: 0 100px 100px 0;
  border: unset;
}
tbody tr td:first-child{
  text-align: start !important;
}
</style>

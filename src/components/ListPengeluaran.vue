<template>
  <table>
    <tr>
      <th>Pengeluaran</th>
      <th>Keterangan</th>
    </tr>
    <tr v-for="(pengeluaran, index) in dataPengeluaran" :key="index">
      <td>{{ pengeluaran.nominal }}</td>
      <td>{{ pengeluaran.keterangan }}</td>
    </tr>
  </table>
</template>

<script>
export default {
  props: {
    dataPengeluaran: Array,
  },
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 100%;
}
table,
th,
td {
  border: 1px solid black;
}
th {
  background-color: magenta;
  color: white;
}
td {
  background-color: orange;
  color: black;
}
tr:hover td {
  background-color: white;
  cursor: pointer;
}
</style>
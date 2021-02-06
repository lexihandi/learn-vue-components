<template>
  <Title title="Catatan Pengeluaran" />
  <ListPengeluaran
    v-if="dataPengeluaran.length > 0"
    :dataPengeluaran="dataPengeluaran"
  />
</template>

<script>
import Title from "./components/Title";
import ListPengeluaran from "./components/ListPengeluaran";
export default {
  name: "App",
  components: {
    Title,
    ListPengeluaran,
  },
  data() {
    return {
      dataPengeluaran: [
        { nominal: 20000, keterangan: "Makan Siang" },
        { nominal: 20000, keterangan: "Makan Malam" },
        { nominal: 15000, keterangan: "Makan Pagi" },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

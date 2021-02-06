<template>
  <Title title="Catatan Pengeluaran" />
  <FormPengeluaran @entry-pengeluaran="entryPengeluaran($event)" />
  <h2>Total Pengeluaran: {{ totalPengeluaran }}</h2>
  <h3 v-if="warning" class="warning">Pengeluaran Anda terlalu banyak</h3>
  <ListPengeluaran v-if="showList" :dataPengeluaran="dataPengeluaran" />
</template>

<script>
import Title from "./components/Title";
import ListPengeluaran from "./components/ListPengeluaran";
import FormPengeluaran from "./components/FormPengeluaran";
export default {
  name: "App",
  components: {
    Title,
    ListPengeluaran,
    FormPengeluaran,
  },
  data() {
    return {
      dataPengeluaran: [
        { nominal: 20000, keterangan: "Makan Siang" },
        { nominal: 20000, keterangan: "Makan Malam" },
        { nominal: 15000, keterangan: "Makan Pagi" },
      ],
      warning: false,
    };
  },
  methods: {
    entryPengeluaran(event) {
      this.dataPengeluaran.push(event);
    },
  },
  computed: {
    showList: function () {
      return this.dataPengeluaran.length > 0;
    },
    totalPengeluaran: function () {
      return this.dataPengeluaran.reduce(
        (accum, item) => accum + parseInt(item.nominal),
        0
      );
    },
  },
  watch: {
    totalPengeluaran: function (val) {
      if (val > 100000) {
        this.warning = true;
      } else {
        this.warning = false;
      }
    },
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

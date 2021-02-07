<template>
  <form class="form-pengeluaran" @submit.prevent="catat">
    <div>
      <label>Pengeluaran</label>
      <input v-model="state.pengeluaran" type="number" id="pengeluaran" />
    </div>
    <div>
      <label>Keterangan</label>
      <input v-model="state.keterangan" type="text" id="keterangan" />
    </div>
    <div>
      <button>Catat</button>
    </div>
  </form>
</template>

<script>
import { reactive } from "vue";
export default {
  setup(props, context) {
    const state = reactive({
      pengeluaran: null,
      keterangan: null,
    });
    function catat() {
      context.emit("entry-pengeluaran", {
        nominal: state.pengeluaran,
        keterangan: state.keterangan,
      });
      state.pengeluaran = null;
      state.keterangan = null;
      document.getElementById("pengeluaran").focus();
    }
    return {
      state,
      catat,
    };
  },
};
</script>

<style scoped>
.form-pengeluaran {
  padding: 20px;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: center;
}

.form-pengeluaran label {
  margin: 5px 10px 5px 0;
  margin-left: 10px;
}

.form-pengeluaran input {
  vertical-align: middle;
  padding: 5px 10px 5px 0;
  margin-right: 10px;
}

.form-pengeluaran button {
  padding: 10px 20px;
  border-radius: 5px;
}

.form-pengeluaran button:hover {
  background-color: magenta;
  cursor: pointer;
  color: white;
}
</style>
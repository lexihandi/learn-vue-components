<template>
  <form class="form-pengeluaran">
    <div>
      <label>Pengeluaran</label>
      <input type="number" id="pengeluaran" />
    </div>
    <div>
      <label>Keterangan</label>
      <input type="text" id="keterangan" />
    </div>
    <div>
      <button>Catat</button>
    </div>
  </form>
</template>

<script>
export default {};
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
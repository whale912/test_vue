<template>

  <table class="board-table">
    <tr class="tb_header">
      <th v-for="(column, i) in colModel" v-bind:key="i"
         :style="{ width: column.width }" scope="col">{{ column.text }}</th>
    </tr>
    <tr class="tb_row" v-for="(rowData, i) in gridData" :key="i">
      <td v-for="(column, i) in colModel" v-bind:key="i" v-bind:style="{textAlign: column.align}"
          v-bind:class="{'border-bottom-zero': gridData.length == listSize}">{{rowData[column.name]}}</td>
    </tr>
  </table>
</template>

<script>
export default {
  name: 'grid',
  props: {
    msg: String,
    colModel: [],
    gridData: [],
    listSize: Number,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.board-table {
  border-collapse: collapse;
  width: 100%;
  font-size: 13px;

}
.board-table th {
  border-bottom: 1px solid #bfbfbf;
  height: 32px;
}

.board-table th:first-child {
  border-left: 0px;
}

.board-table th:last-child {
  border-right: 0px;
}

.board-table .tb_row td {
  border-bottom: 1px solid #bfbfbf;
  height: 32px;
  padding: 0px 10px 0px 10px;
}

.board-table .tb_row td:first-child {
  border-left: 0px;
}
.board-table .tb_row td:last-child {
  border-right: 0px;
}
.border-bottom-zero {
  border-bottom: 0px;
}

</style>

<template>
  <div id="tableDiv" class="table-div">
    <table id="gridTable" class="grid-table">
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Age</th>
      </tr>
      <tr class="list-person" :key="people.nameId" v-for="people in peoples">
        <td>{{ people.fName }}</td>
        <td>{{ people.lName }}</td>
        <td>{{ people.age }}</td>
        <button class="delete-btn" @click="deleteTask">X</button>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Table",
  props: {
    peoples: {
      type: Array,
    }
  },
  methods: {
    deleteTask(id) {
      this.$emit('delete-task', this.id)
    },
  },
};
</script>

<style scoped>
.grid-table {
  color: #fff;
  width: 95%;
  height: auto;
  margin-left: auto;
  margin-right: auto;
}

th,
td {
  border: 0.2rem solid #fff;
  padding-left: 0.2rem;
  position: relative;
}

.table-inputs {
  width: 75%;
  height: 1.5rem;
  border-radius: 1.5rem;
  padding-left: 0.625rem;
  color: black;
  margin-left: 0.5rem;
}

.table-button {
  margin-left: 0.6rem;
}

.delete-btn {
  border-radius: 50%;
  background-color: darkred;
  color: #fff;
  width: 3rem;
  height: 3rem;
  font-size: 18pt;
  cursor: pointer;
  margin-left: 0.1rem;
}

.table-div {
  width: 100%;
  height: auto;
  margin-left: auto;
  margin-right: auto;
  margin-top: -2rem;
}
</style>


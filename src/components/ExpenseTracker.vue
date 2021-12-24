<template>
  <div class="container">
    <h3 id="heading2">Add A New Item:</h3>
    <div class="form-control">
      <label><h2>Name:</h2></label>
      <textarea v-model="description" id="textArea1">
        Where was the expense made?</textarea
      >
    </div>
    <div class="form-control">
      <label><h2>Date:</h2></label>
      <input v-model="date" type="date" id="dateField1" />
    </div>
    <div class="form-control">
      <label><h2>Amount:</h2></label>
      <textarea v-model="amount" id="textArea3"></textarea>
    </div>
    <button @click="myFunction" id="button1">Add Expense</button>

    <table>
      <thead>
        <tr>
          <th><h2>Name</h2></th>
          <th><h2>Date</h2></th>
          <th><h2>Amount</h2></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(row, index) in rows" :key="row.id" :index="index">
          <td>{{ row.description }}</td>
          <td>{{ row.date }}</td>
          <td>{{ row.amount }}</td>
          <td><button @click="onDelete(index)">Remove Expense</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "ExpenseTracker",
  data() {
    return {
      amount: "25 Caps",
      description: "Stimpack",
      date: "",
      rows: [],
    };
  },
  methods: {
    myFunction() {
      // Add Users Input to Table
      console.log("myFunction fired.");
      this.rows.push({
        description: this.description,
        date: this.date,
        amount: this.amount,
      });
      // Clear Input Fields
      this.amount = "";
      this.date = "";
      this.description = "";
    },
    onDelete(index) {
      // Remove Expense from Table
      console.log("onDelete fired.");
      this.rows.splice(index, 1);
    },
  },
};
</script>


<style scoped>
table {
  margin-bottom: 250px;
}
#heading1,
#heading2 {
  text-align: center;
}
label h2,
th h2 {
  font-weight: 400;
  margin: 0;
}
button {
  border-radius: 5px;
  border: 0;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 1.25rem;
  cursor: pointer;
  box-shadow: 0 4px 8px 0 rgb(0 0 0 / 20%), 0 6px 20px 0 rgb(0 0 0 / 19%);
}
.container,
table {
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  margin-top: 10px;
}
th {
  width: 25%;
  font-weight: 400;
  margin: 0;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input,
#textArea1,
#textArea3 {
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
  border-radius: 0.25rem;
  border: 3px solid #515151cf;
  padding: 0.375rem 0.75rem;
  box-shadow: 0 4px 8px 0 rgb(0 0 0 / 20%), 0 6px 20px 0 rgb(0 0 0 / 19%);
  font-family: Arial, Helvetica, sans-serif;
}
</style>

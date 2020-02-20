<script>
  import { setContext } from "svelte";

  const state = {
    name: "a simple name",
    remove: removeExpense
  };
  // components
  import Navbar from "./Navbar.svelte";
  import ExpenseList from "./ExpenseList.svelte";
  // data
  import expenseData from "./expenses";
  // variables
  let expenses = [...expenseData];
  // functions
  function removeExpense(id) {
    expenses = expenses.filter(item => item.id !== id);
  }

  function clearExpenses() {
    expenses = [];
  }

  setContext("state", state);
</script>

<style>

</style>

<Navbar />
<main class="content">
  <ExpenseList {expenses} />
  <button type="button" class="btn btn-primary btn-block" on:click={clearExpenses}>
    clear expenses
  </button>
</main>

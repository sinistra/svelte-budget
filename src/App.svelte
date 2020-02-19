<script>
// components
  import Navbar from "./Navbar.svelte";
  import Title from "./Title.svelte";
  import ExpenseList from "./ExpenseList.svelte";
  // data
  import expenseData from "./expenses";
  // variables
  let expenses = [...expenseData];
</script>

<style>
</style>

<Navbar />
<main class="content">
<ExpenseList {expenses} />
</main>
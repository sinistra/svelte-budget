<script>
  import { getContext } from "svelte";

  export let expense;
  // console.log(expense);
  let displayAmount = false;

  function toggleAmount() {
    displayAmount = !displayAmount;
  }

  const { remove } = getContext("state");
</script>

<article class="single-expense">
  <div class="expense-info">
    <h2>
      {expense.name}
      <button class="amount-btn" on:click={toggleAmount}>
        <i class="fas fa-caret-down" />
      </button>
    </h2>
    {#if displayAmount}
      <h4>Amount: ${expense.amount}</h4>
    {/if}
  </div>
  <div class="expense-buttons" />
  <button class="expense-btn edit-btn">
    <i class="fas fa-pen" />
  </button>
  <button class="expense-btn delete-btn" on:click={() => remove(expense.id)}>
    <i class="fas fa-trash" />
  </button>
</article>

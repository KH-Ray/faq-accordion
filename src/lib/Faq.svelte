<script>
  import iconPlus from "../assets/icon-plus.svg";
  import iconMinus from "../assets/icon-minus.svg";

  export let faq;
  export let isOpen = false;
</script>

<div class="faq-container">
  <p class="faq-title" on:click={() => (isOpen = !isOpen)}>
    <strong>{faq.title}</strong>
    {#if !isOpen}
      <img src={iconPlus} alt="Plus icon" />
    {:else}
      <img src={iconMinus} alt="Minus icon" />
    {/if}
  </p>
  {#if isOpen}
    <p class="faq-content">
      {faq.content}
    </p>
  {/if}
</div>

<style>
  .faq-container {
    font-size: 1.6rem;
    line-height: 2.4rem;
  }

  .faq-title {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 0.4rem;

    color: hsl(292, 42%, 14%);
    font-weight: 600;
    cursor: pointer;
  }

  .faq-title:hover {
    color: #ad28eb;
  }

  .faq-content {
    color: hsl(292, 16%, 49%);
    margin-top: 1.6rem;
  }

  .hidden {
    display: none;
  }
</style>

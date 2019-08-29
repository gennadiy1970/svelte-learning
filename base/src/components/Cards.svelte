<style>
  .cards {
    min-width: 320px;
    max-width: 1200px;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-start;
    box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.1);
    padding: 1rem;
  }
</style>

<div class="cards">
  <slot />
</div>

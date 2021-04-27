<div class="nozzle-setoff" class:nozzle-setoff--disabled={disabled}>
  <button>Set offset</button>
</div>

<script>
  export let disabled
  export let slot
</script>

<style type="text/scss">
  .nozzle-setoff {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;

    button {
      width: 160px;
      height: 50px;
      background-color: var(--darkGray);
      border: 1px solid var(--darkGray);
      border-radius: 3px;
      box-shadow: 0 2px 2px 0 var(--borderGray);
      color: var(--white);
      letter-spacing: 1px;
      cursor: pointer;
    }

    &--disabled {
      button {
        background-color: var(--disabledGray);
        border: 1px solid var(--disabledGray);
        cursor: not-allowed;
      }
    }
  }
</style>

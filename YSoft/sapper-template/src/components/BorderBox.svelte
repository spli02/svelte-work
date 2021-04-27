<div class="border-box" class:border-box--short={isShortBox} class:border-box--tall={!isShortBox}>
  <slot name="left" />
  <div class="border-box__separator" />
  <slot name="right" />
</div>

<script>
  export let boxType
  const isShortBox = boxType === 'short'
</script>

<style type="text/scss">
  .border-box {
    display: flex;
    justify-content: space-between;
    width: 370px;
    border: solid 1px var(--borderLightGray);
    border-radius: 3px;

    &__separator {
      margin: 0;
      width: 1px;
      background-color: var(--borderLightGray);
    }

    &--short {
      height: 120px;
    }

    &--tall {
      height: 212px;
    }
  }
</style>

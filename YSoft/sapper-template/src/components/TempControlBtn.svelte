<div
  class="temp-control-btn"
  class:temp-control-btn--disabled={disabled}
  class:temp-control-btn--on={isStatusOn}
  class:temp-control-btn--heat-on={!isCoolType && isStatusOn}
  class:temp-control-btn--cool-on={isCoolType && isStatusOn}
  on:click={() => !disabled && handleTemp(type)}
>
  <img {src} alt={srcAlt} />
  <span>
    {title}
  </span>
</div>

<script>
  export let title
  export let slot
  export let src
  export let srcAlt
  export let type
  export let isStatusOn
  export let handleTemp
  export let tempControlType
  export let disabled

  const isCoolType = type === tempControlType.COOL
</script>

<style type="text/scss">
  .temp-control-btn {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0;
    width: 100%;
    cursor: pointer;

    img {
      margin-right: 10px;
    }

    span {
      font-size: var(--font-size-big);
      font-weight: 500;
    }

    &--disabled {
      color: var(--disabledGray);
      cursor: not-allowed;
    }

    &--on {
      color: var(--white);
    }

    &--cool-on {
      background-image: linear-gradient(122deg, var(--blue), var(--darkBlue));
    }

    &--heat-on {
      background-image: linear-gradient(122deg, var(--red), var(--darkRed));
    }
  }
</style>

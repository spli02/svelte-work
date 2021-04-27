<div
  class="general-control"
  class:general-control--disabled={disabled}
  on:click={!disabled && handleClick}
>
  <img {src} alt={srcAlt} />
  <div>
    <p>{title}</p>
    {#if subTitle}
      <p class:highlighted={isSubTitleHighlighted}>
        {subTitle || ''}
      </p>
    {/if}
  </div>
</div>

<script>
  export let title
  export let src
  export let srcAlt
  export let subTitle = undefined
  export let isSubTitleHighlighted = undefined
  export let handleClick = undefined
  export let disabled = undefined
</script>

<style type="text/scss">
  .general-control {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    width: 370px;
    height: 75px;
    border: solid 1px var(--borderLightGray);
    border-radius: 3px;
    background-color: var(--white);
    text-align: left;
    cursor: pointer;

    img {
      margin: 0 20px;
    }

    div {
      font-size: var(--font-size-big);
      font-weight: 500;

      p {
        margin: 0;
      }

      p:nth-child(2) {
        margin-top: 10px;
        font-size: var(--font-size-default);
        color: var(--gray);
      }

      p:nth-child(2).highlighted {
        color: var(--orange);
      }
    }

    &--disabled {
      color: var(--disabledGray);
      cursor: not-allowed;

      div {
        p:nth-child(2) {
          color: var(--disabledGray);
        }
      }
    }
  }
</style>

<div class="subtitle">
  <div>
    <img {src} alt={srcAlt} />
    <span>{title}</span>
  </div>

  {#if isProgressRequired}
    <div>
      <progress max="100" value={currentProgress} />
    </div>
  {/if}
</div>

<script>
  export let title
  export let src = undefined
  export let srcAlt = undefined
  export let isProgressRequired = undefined
  export let tempCoolStatus = undefined
  export let tempHeatStatus = undefined

  let currentProgress = 0
  $: tempCoolStatus && tempHeatStatus && resetProgress()

  const resetProgress = () => {
    currentProgress = 0
  }

  setInterval(() => {
    currentProgress = currentProgress + 10
  }, 1000)
</script>

<style type="text/scss">
  .subtitle {
    display: flex;
    justify-content: space-between;
    text-align: left;

    img {
      margin-right: 10px;
      vertical-align: middle;
    }

    span {
      margin: 0;
      vertical-align: middle;
      color: var(--lightBlack);
      font-weight: 100;
      font-size: var(--font-size-big);
    }

    progress {
      text-align: right;
      width: 100px;
    }
  }
</style>

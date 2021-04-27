<div class="nozzle-illustration">
  <img src="../images/illustration.svg" alt="nozzle_illustration" />
  <div>2.20mm</div>
</div>

<script>
  export let slot
</script>

<style type="text/scss">
  @mixin position-center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .nozzle-illustration {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;

    img {
      @include position-center;
    }

    div {
      @include position-center;
      padding: 2px 10px;
      border: 1px solid var(--lightGray);
      border-radius: 15px;
      background-color: var(--lightGray);
      color: var(--white);
      font-size: var(--font-size-default);
    }
  }
</style>

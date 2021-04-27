<div class="application-bar">
  <div class="application-bar__left">
    <img src="../images/icons-20-x-20-network.svg" alt="network" />
    <div class="application-bar__left--circle" />
    10.1.2.198
  </div>

  <p class="application-bar__center">Biology class eDee 1</p>

  <p>Wed 9:53</p>
</div>

<style type="text/scss">
  .application-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    height: 22px;
    padding: 0 3px;
    background-color: var(--barGray);
    color: var(--gray);

    &__left {
      display: flex;
      justify-content: space-between;
      align-items: center;

      &--circle {
        margin: 0 5px;
        height: 10px;
        width: 10px;
        border-radius: 50%;
        background-color: var(--green);
      }
    }

    &__center {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
    }
  }
</style>

<header>
  <a href="./">
    <img src="../images/buttons-oval-back-normal.svg" alt="go_back" />
  </a>

  <h1>Nozzle settings</h1>

  <div class="header-logout">
    <div>
      <p>Fitzwilliam Darcy</p>
      <p>3D Operator</p>
    </div>
    <a href="./">
      <img src="../images/buttons-oval-logout-normal.svg" alt="logout" />
    </a>
  </div>
</header>

<style type="text/scss">
  header {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center;
    position: relative;
    height: 70px;
    padding: 0 10px;
    border-bottom: 1px solid var(--borderGray);

    h1 {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      margin: 0;
      color: var(--orange);
      font-weight: 100;
      font-size: var(--font-size-biggest);
    }

    .header-logout {
      display: flex;
      justify-content: space-between;

      div {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        margin-right: 0.5rem;
        font-weight: 500;

        p {
          margin: 0;
        }

        p:nth-child(2) {
          color: var(--lightBlack);
        }
      }
    }
  }
</style>

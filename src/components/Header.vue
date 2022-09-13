<template>
  <header>
    <img alt="Switchdock" class="logo" src="../assets/logo_white.png" />
    <nav>
      <ul>
        <li>
          <a class="active" href="#">Benefits</a>
        </li>
        <li>
          <a href="#">Safety</a>
        </li>
        <li>
          <a href="#">Policies</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
  header {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 2;
    padding: 0 0 0 1.5em;

    ul {
      display: flex;
      align-items: center;
      padding: 0;

      li {
        list-style: none;

        a {
          font-size: 0.875em;
          line-height: 1;
          color: white;
          background-color: transparent;
          display: block;
          position: relative;
          padding: 1.5em;
          transition: all 333ms ease-in-out;

          &:hover {
            background-color: var(--red);
          }

          &.active::before {
            content: "";
            background-color: var(--red);
            display: block;
            height: 3px;
            width: 100%;
            position: absolute;
            left: 0;
            bottom: 0;
          }
        }
      }
    }
  }

  .logo {
    display: block;
    margin: 0;
    max-width: 280px;
  }

  @media (max-width: 767px) {
    header {
      display: flex;
      flex-flow: column nowrap;
      padding: 1em 2em 0;

      ul li a {
        padding: 1em;

        &:hover {
          background-color: transparent;
        }
      }
    }
  }
</style>

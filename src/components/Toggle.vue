<script>
    export default {
        methods: {
            darkMode() {
                let body = document.querySelector('body');
                body.classList.toggle('dark');
            }
        }
    }
</script>

<template>
    <div class="toggle-switch-wrapper">
        <p>Theme</p>
        <div class="toggle-switch">
            <label>
                <input type="checkbox">
                <span @click="darkMode()" class="track"></span>
            </label>
        </div>
    </div>
</template>

<style scoped lang="scss">

.toggle-switch {
  position: relative;
  width: 66.66px;
  height: 33.33px;
  margin-left: 12px;

  &-wrapper {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding-bottom: 2em;

    p {
        margin: 0;
        font-weight: 600;
        transition: color 333ms ease-in-out;
    }
  }
}

label {
  position: absolute;
  width: 100%;
  height: 33.33px;
  background-color: black;
  border-radius: 50px;
  cursor: pointer;
  z-index: 1;
}

input {
  position: absolute;
  display: none;
}

.track {
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50px;
  transition: 0.3s;
}

input:checked ~ .track {
  background-color: white;
}

.track::before {
  content: "";
  position: absolute;
  top: 4.33px;
  left: 5.33px;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  box-shadow: inset 9.33px -1.33px 0px 0px white;
  background-color: black;
  transition: 0.3s;
}

input:checked ~ .track::before {
  transform: translateX(31.66px);
  background-color: black;
  box-shadow: none;
}

.dark .toggle-switch-wrapper p {
    color: white;
}

@media (max-width: 767px) {
    .toggle-switch-wrapper {
        justify-content: center;
    }
}

</style>
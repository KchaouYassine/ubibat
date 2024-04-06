<template>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

:root{
  --main-red-color: #e74c3c;
  --main-green-color: #0f9c22;
  --main-orange-color: #f0690f;

}
.cursor-pointer{
  cursor: pointer !important;
}

.text-red{
  color: var(--main-red-color);
}
.text-green {
  color: var(--main-green-color);
}
.text-orange {
  color: var(--main-orange-color);
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

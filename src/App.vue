<template>
  <router-view />
</template>

<style lang="scss">
:root{
  --main-red-color: #e74c3c;
  --main-green-color: #0f9c22;
  --main-orange-color: #f0690f;
  --main-black-color: #2c3e50;

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--main-primary-color);
}

.text-black{
  color: var(--main-black-color);
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

.cursor-pointer{
  cursor: pointer !important;
}



</style>

<template>
  <div class="about">
    <h1>This is an <span>about</span> page</h1>
  </div>
</template>

<style scoped lang="scss">
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

h1 {
  color: blue;
  span {
    color: green;
  }
}
</style>

<template>
  <div class="container">
    <div class="left-col">
      <div class="flex-item item-1">Item 1</div>
      <div class="flex-item item-2">Item 2</div>
    </div>
    <div class="center-col">
      <div class="flex-item item-3">Item 3</div>
    </div>
    <div class="right-col">
      <div class="flex-item item-4">Item 4</div>
      <div class="flex-item item-5">Item 5</div>
    </div>
  </div>
</template>
<style lang="css" scoped>
body {
    margin: 0;
}

.container {
    border: 6px solid black;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.left-col,
.center-col,
.right-col {
    display: flex;
    gap: 0.5rem;
}

.left-col,
.right-col {
    flex-shrink: 0;
}

.center-col {
  justify-content: center;
  flex: 2; /* allows it to stay centered */
}

.flex-item {
    color: white;
    font-size: 1.5rem;
    padding: 1rem;
    text-align: center;
}

.item-1 {
    background-color: orange;
}
.item-2 {
    background-color: red;
}
.item-3 {
    background-color: green;
    width: 100%;
    max-width: 300px;
}
.item-4 {
    background-color: blue;
}
.item-5 {
    background-color: yellow;
}
</style>

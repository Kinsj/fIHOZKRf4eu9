<template>
  <div>
    <button><span></span></button>
  </div>
</template>
<style lang="scss" scoped>
  $bh: 22px;
  $sh: $bh - 4px;
  button {
    height: $bh;
    width: $bh * 2;
    border: none;
    background: blue;
    border-radius: $bh / 2;
    position: relative;
    > span {
      position: absolute;
      top: 2px;
      left: 2px;
      height: $sh;
      width: $sh;
      background: white;
      border-radius: 50%;
      transition: left .3s ease;
    }
    &:hover > span {
      left: calc(100% - #{$sh} - 2px);
    }
  }
</style>
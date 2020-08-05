<template>
  <div>
    <button :class="{checked}" @click="toggleChecked"><span></span></button>
  </div>
</template>
<script>
import {ref} from 'vue'
export default {
  setup() {
    const checked = ref(false);
    const toggleChecked = () => {checked.value = !checked.value}
    return {checked, toggleChecked}
  }
}
</script>
<style lang="scss" scoped>
  $bh: 22px;
  $sh: $bh - 4px;
  button {
    height: $bh;
    width: $bh * 2;
    border: none;
    background: gray;
    border-radius: $bh / 2;
    position: relative;
    cursor: pointer;
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
    &.checked{
      background: blue;
      > span {
        left: calc(100% - #{$sh} - 2px);
      }
    } 
    &:focus {
      outline: none;
    }
  }
</style>
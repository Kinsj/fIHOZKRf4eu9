<template>
  <div>
    <button :class="{checked}" @click="toggle"><span></span></button>
  </div>
</template>
<script>
import {ref} from 'vue'
export default {
  props: {
    checked: Boolean
  },
  setup(props, context) {

    const toggle = () => {
      context.emit('update:checked', !props.checked)
    }

    return {toggle}
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
    background: rgba(0,0,0,.25);
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
      background: #1890ff;
      > span {
        left: calc(100% - #{$sh} - 2px);
      }
    } 
    &:focus {
      outline: none;
    }
  }
</style>
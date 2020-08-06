<template>
  <div>
    <Switch v-model:checked="checked" />
  </div>
</template>
<script lang="ts">
import Switch from '../lib/Switch.vue'
import {ref} from 'vue'
export default {
  setup() {
    const checked = ref(false)
    return {
      checked
    }
  },
  components: {
    Switch
  }
}
</script>
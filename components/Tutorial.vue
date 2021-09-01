<template lang="pug">
button(@click='res.Click') Enable {{ res.enable }}
</template>
<script>
import { defineComponent, reactive } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const res = reactive({
      enable: false,
      Click: () => {
        res.enable = !res.enable
      },
    })
    return { res }
  },
})
</script>

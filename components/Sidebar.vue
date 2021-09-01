<template lang="pug">
.sidebar.d-none.d-md-block
  //- .mini
  b-navbar.b-b
    .flex
      img(
        v-if='res.themeClass',
        src='https://i.imgur.com/GnVzAsm.png',
        height='35'
      )
      img(v-else, src='https://i.imgur.com/G9RoUuv.png', height='35')

  .flex.pt-3
    .smenu
      ul.smn
        li.head Dashboard
        li.menu(title='Sales Monitoring')
          .micon 
            i.mdi.mdi-monitor.mdi-18px
          .mtitle Sales Monitoring
        li.menu
          .micon 
            i.mdi.mdi-account.mdi-18px
          .mtitle Helpdesk Management
        li.menu
          .micon 
            i.mdi.mdi-merge.mdi-18px
          .mtitle File Manager

      ul.smn
        li.head Dashboard
        li.menu
          .micon 
            i.mdi.mdi-monitor.mdi-18px
          .mtitle Sales Monitoring
          .mcount
            b-badge.bg-success 1
        li.menu
          .micon 
            i.mdi.mdi-account.mdi-18px
          .mtitle Helpdesk Management
        li.menu
          .micon 
            i.mdi.mdi-merge.mdi-18px
          .mtitle File Manager

      ul.smn.noicon
        li.head Dashboard
        li.menu Sales Monitoring
        li.menu Helpdesk Management
        li.menu File Manager
</template>
<script>
import { onMounted, reactive } from '@nuxtjs/composition-api'
export default {
  components: {},
  setup() {
    const res = reactive({
      themeClass: true,
      clickL: () => {
        res.themeClass = !res.themeClass
      },
    })
    onMounted(() => {})
    return { res }
  },
  head() {
    return {
      bodyAttrs: {
        class: this.res.themeClass ? 'bg-dark' : '',
      },
    }
  },
}
</script>
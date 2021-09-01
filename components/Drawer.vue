<template lang="pug">
b-sidebar#sidebar-right(
  title='Sidebar',
  left,
  shadow,
  width='240px',
  bg-variant='white'
)
  .flex.mt-2
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
import Sidebar from './Sidebar'
export default {
  components: {
    Sidebar,
  },
}
</script>
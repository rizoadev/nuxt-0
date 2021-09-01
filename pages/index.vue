<template lang="pug">
.flex.d-flex
  //- =======================================
  //- Sidebar
  //- =======================================
  Sidebar

  .flex.flex-grow-1
    //- =======================================
    //- main nav
    //- =======================================
    b-navbar.navbar.navbar-expand-sm.b-b.mainav
      .mr-1.dc.d-md-none
        img(
          v-if='res.themeClass',
          src='https://i.imgur.com/GnVzAsm.png',
          height='35'
        )
        img(v-else, src='https://i.imgur.com/G9RoUuv.png', height='35')

      b-navbar-nav.pt-2
        b-nav-item.pointer.d-none.d-md-block(style='margin-top: -2px')
          i.mdi.mdi-menu.mdi-24px.text-muted

      ul.nav.navbar-menu.order-0.order-lg-2.border-0
        b-nav-item.ml-2(v-b-toggle.sidebar-right)
          i.mdi.mdi-merge.mdi-24px.text-muted

        b-nav-item
          button.btn.btn-sm.btn-icon
            i.mdi.mdi-bell-outline.text-muted.mdi-18px
              .bcount 12

        b-nav-item
          button.btn.btn-sm.btn-icon(@click='res.clickL')
            i.mdi.mdi-weather-night.mdi-18px.text-muted

        b-nav-item
          button.btn.btn-sm.btn-icon(@click='res.clickL')
            i.mdi.mdi-white-balance-sunny.text-muted.mdi-18px

        b-nav-item-dropdown.ml-2(right, no-caret)
          template(v-slot:button-content)
            b-avatar(size='28px', variant='light', circle, text='AV') 
          b-dropdown-item.b-b(disabled)
            h6 menu down
          b-dropdown-item.flex
            .flex.d-flex.w-md.pt-1.pb-2

        b-nav-item.ml-2.d-md-none
          i.mdi.mdi-menu.mdi-24px.text-muted

    //- =======================================
    //- container
    //- =======================================
    .flex
      .container
        .flex {{ res.themeClass }}
        .flex.py-3
          Table.table.table-theme.v-middle.table-hover.table-condensed
        .flex.py-3
          //-Alert
          Form 
          Drawer
</template>
<script>
import { onMounted, reactive } from '@nuxtjs/composition-api'
import Form from '~/components/Form'
import Table from '~/components/Table'
import Alert from '~/components/Alert'
import Sidebar from '~/components/Sidebar'

export default {
  components: {
    Form,
    Table,
    Alert,
    Sidebar,
  },
  setup() {
    const res = reactive({
      themeClass: false,
      clickL: () => {
        require('consola').info('asasas')
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
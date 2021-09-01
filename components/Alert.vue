

<template>
  <div>
    <b-alert show dismissible class="my-1">Default Alert</b-alert>
    <b-alert variant="success" show class="my-1">Success Alert</b-alert>
    <b-alert variant="danger" show class="my-1">Success Alert</b-alert>
    <b-alert variant="info" show class="my-1">Success Alert</b-alert>
    <b-alert variant="primary" show class="my-1">Success Alert</b-alert>
    <b-alert variant="warning" show class="my-1">Success Alert</b-alert>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dismissSecs: 10,
      dismissCountDown: 0,
      showDismissibleAlert: false,
    }
  },
  methods: {
    countDownChanged(dismissCountDown) {
      this.dismissCountDown = dismissCountDown
    },
    showAlert() {
      this.dismissCountDown = this.dismissSecs
    },
  },
}
</script>
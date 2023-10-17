<template>
  <qrcode-vue :value="value" :size="size" level="H" />
</template>

<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: window.location.origin + window.location.pathname,
        size: 300,
      }
    },
    components: {
      QrcodeVue,
    },
  }
</script>

<template>
  <div class="header">{{seller.name}}</div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      seller: {
        type: Object,
        default: '名字'
      }
    }
  }
</script>

<style >
</style>

<template>
  <header class="pro-header">
产品管理
  </header>
</template>

<script>
export default {
  name: 'HelloWorld',

}
</script>

<style scoped lang="scss">
  $content-wide:1280px;
  $header-height:40px;
  .pro-header{
    max-width: $content-wide;
    max-height: $header-height;
    line-height: $header-height;
    background-color: rgb(255, 255, 255);
    padding-left: 15px;
    margin-left: auto;
    margin-right: auto;
  }


</style>

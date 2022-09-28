<template>
  <!-- <Tutorial/> -->
  <div>
    <h1>{{ $t("home") }}</h1>
    <div>language : {{ locale }}</div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      locale: this.$i18n.locale
    }
  },
}
</script>

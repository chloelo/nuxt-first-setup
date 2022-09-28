<template>
  <main>
    <div>
      <h1>{{ $t("about") }}</h1>
      <div>language : {{ locale }}</div>
    </div>
    <!-- <h1>{{ $t('greeting') }}</h1>

    <nuxt-link
      v-if="$i18n.locale !== 'en'"
      :to="switchLocalePath('en')"
    >
      English
    </nuxt-link>

    <nuxt-link
      v-if="$i18n.locale !== 'tw'"
      :to="switchLocalePath('tw')"
    >
      中文
    </nuxt-link>
    <p>{{ $t('content')}}</p> -->
    <!-- <h1>{{ $t('greeting') }}</h1>
    <a href="#" @click="$router.push(localeLocation({ name: 'IndexPage', params: { foo: '1' } }))">Navigate</a> -->
  </main>
</template>
<script>
export default {
  name: 'about',
  data() {
    return {
      locale: this.$i18n.locale
    }
  },
}
</script>
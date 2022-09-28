<template>
  <div>
    <div>
      <!-- <a :href="$i18n.locale === 'tw' ? '/en' : '/tw'">
          <span>Switch Language</span>
        </a> -->
      <!-- <a @click.prevent="switchLang">
          <span>Switch Language</span>
        </a> -->
      <select v-model="locale">
        <option value="tw" selected>中文</option>
        <option value="en">English</option>
      </select>
      <!-- <nuxt-link
        v-for="locale in availableLocales"
        :key="locale.code"
        :to="switchLocalePath(locale.code)"
        >{{ locale.name }}</nuxt-link
      > -->
    </div>
    <h4>Router Links:</h4>
    <div>
      <nuxt-link to="/">
        <span>{{ $t("home") }}</span>
      </nuxt-link>
      <nuxt-link to="/about">
        <span>{{ $t("about") }}</span>
      </nuxt-link>
    </div>
    <main>
      <Nuxt />
    </main>
  </div>
</template>
<script>
export default {
  name: "default",
  data() {
    return {
      locale: "tw",
    };
  },
  methods: {
    // getLan() {
    //   console.log(this.locale, "getLen");
    //   this.$i18n.locale = this.locale;
    // },
    // switchLang({key}){
    //   this.route.query.lang = this.$i18n.locale === 'tw' ? 'en' : 'tw';
    //   this.$i18n.locale = this.$i18n.locale === 'tw' ? 'en' : 'tw';
    // }
  },
  computed: {
    availableLocales () {
      return this.$i18n.locales.filter(i => i.code !== this.$i18n.locale)
    }
  },
  // computed: {
  //   localeLocation() {
  //     return this.$i18n.locale === 'tw' ? '/tw' : '/en';
  //   },
  watch: {
    locale(val) {
      this.$i18n.setLocale(val); // nuxt-i18n 的 setLocale 方法
      // this.$i18n.locale = val; // vue-i18n 的 setLocale 方法
      // this.$router.replace({query:  {lang: val}})
    },
  },
};
</script>
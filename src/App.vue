<template>
  <select name="lang" v-model='lang'>
    <option value="en">eng</option>
    <option value="ru">rus</option>
    <option value="kz">kaz</option>
  </select>
  <h1>{{ translate('welcome') }}</h1>
  <p>{{ translate('message') }}</p>
</template>

<script>
import en from './lang/en.js';
import ru from './lang/ru.js';
import kz from './lang/kz.js';

export default {
  mixins: [en, ru, kz],
  data() {
    return {
      lang: 'kz',
    }
  },
  methods: {
    translate(prop) {
      return this[this.lang][prop];
    }
  }
}
</script>

<style>

</style>

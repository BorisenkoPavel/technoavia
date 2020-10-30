<template>
  <div class="fruits">
    <div class="fruits-title">{{currentFruit}}</div>
    <input maxlength="2" class="fruits-input" v-model="current" @input="onInput"/>
  </div>
</template>

<script>
export default {
  data () {
    return {
      current: 1,
      fruits: ['яблоко', 'груша', 'банан', 'киви', 'ананас', 'папайя', 'мандарин', 'апельсин', 'айва', 'лимон']
    }
  },
  computed: {
    currentFruit() {
      return this.fruits[this.current - 1]
    }
  },
  methods: {
    onInput({target}) {
      const
          val = target.value,
          twoSymbols = +val.slice(-2),
          newVal = +twoSymbols < 11 && +twoSymbols > 0 ? +val : (+val.slice(-1) || 1)
      if (val !== newVal) {
        target.value = newVal;
        target.dispatchEvent(new Event('input'));
      }
    }
  }
}
</script>

<style scoped lang="scss">
  .fruits {
    width: 388px;
    height: 254px;
    background-color: rgba(255, 255, 255, 0.42);
    border-radius: 8px;
    font-size: 36px;
    text-align: center;
    padding: 44px 30px;
  }
  .fruits-title {
    text-transform: capitalize;
    margin-bottom: 16px;
    height: 77px;
  }
  .fruits-input {
    font-size: 36px;
    line-height: 42px;
    width: 124px;
    outline: none;
    border: none;
    text-align: center;
  }
</style>

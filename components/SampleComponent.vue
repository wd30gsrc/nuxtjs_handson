<template lang="html">
  <div>
    <h1>{{ title }}</h1>
    <div class="">
      Hello, I'm {{ name }}
    </div>
    <div>
      {{ reversName }}
    </div>
    <button type="button" name="button" @click="plus">
      {{ num }}
    </button>
    <div :class="['hide', {seven: num === 7}]">
      click 7 times
    </div>
    <div slot="named" class="blue">
      <slot name="named" />
    </div>
    <div class="slot">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default Title'
    }
  },
  data () {
    return {
      name: 'vuejs taro',
      num: 0
    }
  },
  computed: {
    reversName () {
      return this.name.split('').reverse().join('')
    }
  },
  mounted () {
    console.log('mounted')
  },
  methods: {
    plus () {
      this.num++
    }
  }
}
</script>

<style lang="scss" scoped>
  .hide {
    display: none;
    &.seven {
      display: block;
    }
  }
  .slot {
    color: red;
  }
  .blue {
    color: blue;
  }
</style>

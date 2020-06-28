<template>
  <section>
    <sample-component :title="indexTitle">
      <div class="come">
        slot example
      </div>
      <div slot="named">
        this is named slot
      </div>
    </sample-component>
    <nuxt-link to="/about">
      About
    </nuxt-link>
  </section>
</template>

<script>
import SampleComponent from '~/components/SampleComponent.vue'

export default {
  components: {
    SampleComponent
  },
  data () {
    return {
      indexTitle: 'Nuxt.js Handson!'
    }
  }
}
</script>

<style>

</style>

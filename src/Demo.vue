<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <gnh-activity-modal
      :closeBtn="require('./assets/close-btn.png')"
      :topImg="require('./assets/reward_mask.png')"
      :centerIcon="require('./assets/reward_success_icon.png')"
      @onClick="clickHandle"
      :show="modalShow"/>
  </div>
</template>

<script>
import GnhActivityModal from './gnh-activity-modal'
import { setTimeout } from 'timers'

export default {
  name: 'demo',
  data () {
    return {
      modalShow: false
    }
  },
  components: {
    [GnhActivityModal.name]: GnhActivityModal
  },
  methods: {
    clickHandle (e) {
      console.log(e)
      this.modalShow = false
    }
  },
  created () {
    setTimeout(() => {
      this.modalShow = true
    }, 1000)
  }
}
</script>
<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
</style>

<template>
  <div id="app">
    <img @click="showModal" alt="Vue logo" src="./assets/logo.png" />
    <gnh-activity-modal
      ref="modal"
      :closeBtn="require('./assets/close-btn.png')"
      :topImg="require('./assets/reward_mask.png')"
      :centerIcon="require('./assets/has_bought.png')"
      @onHide="onHide"
      centerIconWidth="57"
      @onClick="clickHandle"
      />
  </div>
</template>

<script>
import GnhActivityModal from './gnh-activity-modal'

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
  created () {
    setInterval(() => {
      console.log(this.modalShow)
    }, 1000)
  },
  methods: {
    clickHandle (e) {
      console.log(e)
      // this.$refs.modal.toggle()
      this.$refs.modal.$hide()
    },
    showModal () {
      // this.$refs.modal.toggle()
      this.$refs.modal.$show()
    },
    onHide () {
      console.log('hide')
    }
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

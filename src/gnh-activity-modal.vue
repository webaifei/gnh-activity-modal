<template>
  <div class="withdraw-dialog">
    <md-landscape v-model="show" :has-mask="hasMask" :mask-closable="maskClosable">
      <section class="dialog">
        <img class="top-img" :src="topImg" alt="">
        <slot name="close-btn">
          <img
            class="dialog-close"
            @click.self.stop="show = false"
            :src="closeBtn"
          />
        </slot>
        <slot name="modal-center">
          <img class="center-icon" :src="centerIcon" alt="" />
        </slot>
        <p v-if="contentTitle" class="content-title">{{contentTitle}}</p>
        <p v-if="contentSubTitle" class="content-subtitle">{{contentSubTitle}}</p>
        <slot name="modal-bottom">
          <div class="dialog-btn" @click.self.stop="clickHandle">{{btnText}}</div>
        </slot>
      </section>
    </md-landscape>
  </div>
</template>

<script>
import { Landscape } from 'mand-mobile'
export default {
  name: 'gnh-activity-modal',
  props: {
    show: {
      type: Boolean,
      default: true
    },
    topImg: {
      type: String
    },
    centerIcon: {
      type: String
    },
    closeBtn: {
      type: String,
      default: 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyNpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTQwIDc5LjE2MDQ1MSwgMjAxNy8wNS8wNi0wMTowODoyMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIChNYWNpbnRvc2gpIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOjgzOUNGQTc5OUVEMDExRTlCMThBOTlBMUFCOTNCQzYxIiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOjgzOUNGQTdBOUVEMDExRTlCMThBOTlBMUFCOTNCQzYxIj4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6ODM5Q0ZBNzc5RUQwMTFFOUIxOEE5OUExQUI5M0JDNjEiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6ODM5Q0ZBNzg5RUQwMTFFOUIxOEE5OUExQUI5M0JDNjEiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz5zzg3QAAAA1klEQVR42rxWMQ7DIAwkDHkEldj6/wdly1pl6lSGuk5qKoIA2abkpEskg+8CAcMEACaBRb5NH04aNmlwyAfSd4h70nC/yD4C5A35hC9eSE9xCT3lAmm5Y3bwYZEbnCE1ScUjdk3b6sA1aeayO2rEcwOpCauvUSayP0QzdNFUTtlGy9f0gpyTWKB3Hrsj15JIy6BmYrji+U4uYSWBoBHnGHTDMmpLbYpmavNag9pPDiKT0cv08o02tFQMLXZDy/UlB87QIzPSkatGPDXZonipmv792vIRYAAiPuF/TyNMvwAAAABJRU5ErkJggg=='
    },
    contentTitle: {
      type: String,
      default: '确认加速该订单吗'
    },
    contentSubTitle: {
      type: String,
      default: '确认后不可修改'
    },
    btnText: {
      type: String,
      default: '确认'
    },
    hasMask: {
      type: Boolean,
      default: true
    },
    maskClosable: {
      type: Boolean,
      default: true
    }
  },
  data () {
    return {
    }
  },
  components: {
    [Landscape.name]: Landscape
  },
  methods: {
    clickHandle (e) {
      this.$emit('onClick', e)
    }
  }
}
</script>

<style lang="stylus">
p
  margin 0
  padding 0
.withdraw-dialog
  font-size 14px
  color #333
  .md-landscape-content
    width 375px
  .md-landscape
    .md-icon.md-landscape-close
      display none
  .dialog
    overflow hidden
    position relative
    width 302px
    margin 0 auto
    border-radius 14px
    background #fff
    text-align center
    &-close
      position absolute
      width 12px
      height 12px
      left 15px
      top 15px
    .top-img
      position aboslute
      top 0
      left 0
      width 100%
    .center-icon
      margin-top 15px
      display inline-block
      width 82px
      height 82px
    .content-title
      font-size 16px
      line-height 25px
    .content-subtitle
      font-size 14px
    &-btn
      display flex
      justify-content center
      align-items center
      width 220px
      height 40px
      margin 15px auto 30px
      border-radius 20px
      color #fff
      letter-spacing 2px
      background linear-gradient(to top, #fc5037, #fca135)
      font-size 16px
</style>

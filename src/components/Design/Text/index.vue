<template>
  <div :id="elementId" class="text-component">
    <span class="detail" :style="getTextStyle">{{ text }}</span>
  </div>
</template>
<script>
export default {
  props: {
    elementId: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    },
    isBold: {
      type: Boolean,
      default: false
    },
    hasBorder: {
      type: Boolean,
      default: false
    },
    fontFamily: {
      type: String,
      default: '',
    },
    fontSize: {
      type: String,
      default: '',
    },
    lineHeight: {
      type: String,
      default: '',
    },
  },
  computed: {
    getTextStyle() {
      const { fontFamily, fontSize, lineHeight, isBold, hasBorder } = this;
      let style = {}
      style = {
        fontFamily,
        fontSize,
        lineHeight,
        fontWeight: isBold ? 'bold' : '400',
        border: hasBorder ? '1px solid #000' : '1px solid transparent'
      }
      return style
    }
  },
  mounted() {
    this.init()
  },
  methods: {
    init() {
      this.$emit('complete')
      console.log(this.text)
    }
  }
}
</script>

<style lang="scss">
.text-component {
    .detail {
        display: inline-block;
        font-weight: normal;
        word-break: break-all;
        word-wrap: break-word;
        border: 1px solid transparent;
    }
}
</style>


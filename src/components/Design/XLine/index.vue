<template>
  <div class="x-line-warp" :style="getStyle" />
</template>

<script>
export default {
  props: {
    elementId: {
      type: String,
      default: ''
    },
    height: {
      type: [String, Number],
      default: 1
    },
    width: {
      type: [String, Number],
      default: 100
    }
  },
  data() {
    return {
    }
  },
  computed: {
    getStyle() {
      const { height, width } = this
      return {
        backgroundColor: '#000',
        height: `${height}px`,
        minWidth: `${width}px`
      }
    }
  },
  mounted() {
    this.init()
  },
  methods: {
    init() {
      this.$emit('complete')
    }
  }
}
</script>

<style lang="scss">
  .x-line-warp {
  }
</style>

<template>
    <div :style="[gridStyle, responsive]">
        <slot></slot>
    </div>
</template>

<script>
export default {
  props: {
    auto: {
      type: String,
      validator: function (value) {
        return ['fit', 'fill'].includes(value)
      }
    },
    columns: {
      type: [Number, Array],
      default: 2
    },
    gap: String,
    minWidth: {
      type: String,
      default: '10em'
    },
    breakPoint: {
      type: String,
      default: '30em'
    }
  },
  computed: {
    gridStyle () {
      let columns = ''
      if (this.auto) {
        columns = `repeat(auto-${this.auto}, minmax(${this.minWidth}, 1fr))`
      } else {
        if (Array.isArray(this.columns)) {
          columns = this.columns.map(i => `${i}fr`).join(' ')
        } else {
          columns = `repeat(${this.columns}, 1fr)`
        }
      }

      return {
        'display': 'grid',
        'grid-template-columns': columns,
        'grid-gap': this.gap
      }
    }
  }
}
</script>

<style module>

</style>

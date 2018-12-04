<template>
	<div :class="classes"></div>
</template>

<script>
  export default {
    props: {
      split: {
        validator(value) {
          return ['vertical', 'horizontal'].indexOf(value) >= 0
        },
        required: true
      },
      className: String
    },
    computed: {
      classes() {
        const classes = ['splitter-pane-resizer', this.split, this.className]
        return classes.join(' ')
      }
    }
  }
</script>

<style scoped>
.splitter-pane-resizer {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  background: #4AB7BD;
  box-sizing: border-box;
  position: absolute;
  z-index: 1;
}

.splitter-pane-resizer.horizontal {
  height: 10px;
  margin-top: -5px;
  cursor: row-resize;
  width: 100%;
}

.splitter-pane-resizer.vertical {
  width: 10px;
  height: 100%;
  margin-left: -5px;
  cursor: col-resize;
}
</style>

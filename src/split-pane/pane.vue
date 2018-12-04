<template>
	<div :class="classes">
		<slot></slot>
	</div>
</template>

<script>
  export default {
    name: 'Pane',
    props: {
      className: String,
      split: String
    },
    computed: {
      classes() {
        const classes = [this.split, this.className]
        return classes.join(' ')
      }
    },
    data() {
      return {
        percent: 50
      }
    }
  }
</script>

<style scoped>
.splitter-pane {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.splitter-pane.vertical.splitter-paneL {
  position: absolute;
  left: 0;
  height: 100%;
  padding-right: 5px;
}

.splitter-pane.vertical.splitter-paneR {
  position: absolute;
  right: 0;
  height: 100%;
  padding-left: 5px;
}

.splitter-pane.horizontal.splitter-paneL {
  position: absolute;
  top: 0;
  width: 100%;
  padding-bottom: 5px;
}

.splitter-pane.horizontal.splitter-paneR {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding-top: 5px;
}
</style>

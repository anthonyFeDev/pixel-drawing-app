<template>
  <div id="app">
    <ColorPicker :color=color />
    <Canvas :pixels=pixels />
  </div>
</template>
<script>
import Canvas from './components/Canvas.vue'
import ColorPicker from './components/ColorPicker.vue'

const defaultColor = 'white'

export default {
  name: 'App',
  data: function() {
    return {
      color: defaultColor,
      pixels: Array(30 * 30).fill().map(() => defaultColor)
    }
  },
  components: {
    Canvas,
    ColorPicker
  },
  mounted() {
    this.$root.$on('updatecolor', color => {
      this.color = color
    }),
    this.$root.$on('clickedpixel', index => {
      this.pixels.splice(index, 1, this.color)
    })
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>

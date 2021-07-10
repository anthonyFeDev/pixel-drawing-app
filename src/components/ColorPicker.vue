<template>
  <div>
    <Pixel isInColorPicker color="white" :current="color == 'white' ? true : false" />
    <Pixel isInColorPicker color="lightblue" :current="color == 'lightblue' ? true : false" />
    <Pixel isInColorPicker color="blue" :current="color == 'blue' ? true : false" />
    <Pixel isInColorPicker color="darkblue" :current="color == 'darkblue' ? true : false" />
  </div>
</template>
<script>
import Pixel from '../components/Pixel.vue'

export default {
  name: 'ColorPicker',
  components: {
    Pixel
  },
  props: {
    color: String,

  }
}
</script>
<style scoped>

</style>
<template>
  <div>
    <Pixel color="white" :current="color == 'white' ? true : false" />
    <Pixel color="lightblue" :current="color == 'lightblue' ? true : false" />
    <Pixel color="blue" :current="color == 'blue' ? true : false" />
    <Pixel color="darkblue" :current="color == 'darkblue' ? true : false" />
  </div>
</template>
<script>
import Pixel from '../components/Pixel.vue'

export default {
  name: 'ColorPicker',
  components: {
    Pixel
  }
}
</script>
<style scoped>

</style>
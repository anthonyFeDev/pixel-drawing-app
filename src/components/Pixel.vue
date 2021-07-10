<template>
  <div @click="handleClick" :class="['pixel', color, current ? 'current' : '']"></div>
</template>
<script>
export default {
  name: 'Pixel',
  props: {
    color: String,
    current: Boolean,
    interactive: Boolean,
    isInColorPicker: Boolean,
    isInCanvas: Boolean,
    index: Number
  },
  methods: {
    handleClick: function() {
      if(this.isInColorPicker) {
        this.$root.$emit('updatecolor', this.color)
      }
      if(this.isInCanvas) {
        this.$root.$emit('clickedpixel', this.index)
      }
    }
  }
}
</script>
<style scoped>
  .pixel {
    border: 1px solid lightgray;
    width: 30px;
    height: 30px;
    box-sizing: border-box;
  }

  .pixel.current {
    border: 4px solid yellow;
  }

  .white {
    background-color: white;
  }

  .lightblue {
    background-color: lightskyblue;
  }

  .blue {
    background-color: blue;
  }

  .darkblue {
    background-color: darkblue;
  }
</style>
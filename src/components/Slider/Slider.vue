<style>
  .noUi-horizontal {
    height: 5px;
}
</style>
<template>
  <div id="sliderRegular" class="slider slider-info noUi-target noUi-ltr noUi-horizontal" @click="setSlider">
    <div class="noUi-base">
      <div class="noUi-connect" :style="{'left': '0','right': `${widthPercComplement}%`}"></div>
      <div class="noUi-origin" :style="{'left': `${widthPerc}%`}">
        <div class="noUi-handle noUi-handle-lower" :class="{'noUi-active': active}" data-handle="0" style="z-index: 4;"
             @click="toggleActive"></div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'n-slider',
    props: {
      value: {
        type: Number,
        default: 0
      },
      min: Number,
      max: {
        type: Number,
        default: 100
      },
      color: String
    },
    computed: {
      widthPerc() {
        return this.value * this.max / 100
      },
      widthPercComplement() {
        return 100 - this.widthPerc
      }
    },
    data() {
      return {
        active: false
      }
    },
    methods: {
      toggleActive() {
        this.active = !this.active
      },
      setSlider() {
        console.log('set slider')
        console.log(this.$el.offsetY)
      }
    }
  }
</script>
<style>
</style>

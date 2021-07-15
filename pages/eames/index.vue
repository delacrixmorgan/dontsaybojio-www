<template>
  <div>
    <model-viewer
      id='viewer'
      class='viewer'
      src='/models/sheen_chair.glb'
      auto-rotate camera-controls field-of-view='45deg'
      interaction-prompt='none'
      environment-image='neutral'
      option='Peacock Velvet'
      ar ar-modes='webxr scene-viewer quick-look' />

    <div class='relative mx-4'>
      <select
        v-model.lazy='selectedVariant'
        class='block
              w-full
              appearance-none
              bg-grey-lighter
              border border-grey-lighter
              text-grey-darker
              py-3
              px-4
              pr-8
              rounded'
        @change='onVariantSelected($event)'>
        <option v-for='variant in variants' :key='variant'>
          {{ variant }}
        </option>
      </select>
      <div
        class='
      pointer-events-none
      absolute
      inset-y-0
      right-0
      flex
      mr-4
      items-center
      text-grey-darker
    '
      >
        <svg class='h-4 w-4' xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'>
          <path
            d='M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z'
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
import ('@google/model-viewer/dist/model-viewer')

export default {
  data() {
    return {
      viewer: null,
      selectedVariant: '',
      variants: []
    }
  },
  mounted() {
    this.viewer = this.$el.querySelector('model-viewer#viewer')
    this.viewer.addEventListener('load', this.loadVariants(this.viewer))
  },
  methods: {
    loadVariants(viewer) {
      return () => {
        this.variants = viewer.availableVariants
        if (this.variants.length > 0) {
          this.selectedVariant = viewer.availableVariants[0]
          viewer.variantName = this.selectedVariant
        }
      }
    },
    onVariantSelected(event) {
      this.viewer.variantName = this.selectedVariant
    }
  }
}
</script>

<style scoped>
#viewer {
  width: 100%;
  height: 48rem;
}
</style>

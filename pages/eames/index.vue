<template>
  <div>
    <model-viewer
      id='viewer'
      class='w-full h-screen'
      src='/sheen_chair.glb'
      auto-rotate camera-controls field-of-view='45deg'
      interaction-prompt='none'
      environment-image='neutral'
      option='Peacock Velvet'
      ar ar-modes='webxr scene-viewer quick-look' />
  </div>
</template>

<script>
import('@google/model-viewer')

export default {
  created() {
    // const modelViewerVariants = this.document.querySelector('model-viewer#viewer')
    // const select = this.document.querySelector('#variant')
    //
    // modelViewerVariants.addEventListener('load', () => {
    //   const names = modelViewerVariants.availableVariants
    //   for (const name of names) {
    //     const option = this.document.createElement('option')
    //     option.value = name
    //     option.textContent = name
    //     select.appendChild(option)
    //   }
    // })
    //
    // select.addEventListener('input', (event) => {
    //   modelViewerVariants.variantName = event.target.value
    // })
  }
}
</script>

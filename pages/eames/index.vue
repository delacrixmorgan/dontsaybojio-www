<template>
  <div>
    <model-viewer
      id='viewer'
      class='w-full h-screen'
      src='@/public/assets/Astronaut.glb'
      autoplay camera-controls field-of-view='45deg'
      interaction-prompt='none'
      ar ar-modes='webxr scene-viewer quick-look'></model-viewer>
  </div>
</template>

<script>
import('@google/model-viewer')
export default {}
</script>

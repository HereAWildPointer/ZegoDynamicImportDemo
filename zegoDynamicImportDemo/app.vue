<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
  </div>
</template>

<script lang="ts" setup>
const zg = ref()

onMounted(async () => {
  const ZegoExpressEngine = (await import('zego-express-engine-webrtc/esm'))
    .ZegoExpressEngine
  zg.value = new ZegoExpressEngine(appID, server)
  zg.value.setDebugVerbose(false)
})
</script>

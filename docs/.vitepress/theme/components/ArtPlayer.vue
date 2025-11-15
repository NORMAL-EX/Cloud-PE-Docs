<template>
  <div ref="artRef" class="art-player-container"></div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
import Artplayer from 'artplayer'

const props = defineProps<{
  url: string
  poster?: string
  title?: string
}>()

const artRef = ref<HTMLDivElement>()
let art: Artplayer | null = null

onMounted(() => {
  if (!artRef.value) return

  // 获取 VitePress 品牌色
  const brandColor = getComputedStyle(document.documentElement)
    .getPropertyValue('--vp-c-brand-1')
    .trim() || '#3451b2'

  art = new Artplayer({
    container: artRef.value,
    url: props.url,
    poster: props.poster || '',
    title: props.title || '',
    volume: 0.5,
    isLive: false,
    muted: false,
    autoplay: false,
    pip: true,
    autoSize: true,
    autoMini: true,
    screenshot: true,
    setting: true,
    loop: false,
    flip: true,
    playbackRate: true,
    aspectRatio: true,
    fullscreen: true,
    fullscreenWeb: true,
    subtitleOffset: true,
    miniProgressBar: true,
    mutex: true,
    backdrop: true,
    playsInline: true,
    autoPlayback: true,
    airplay: true,
    theme: brandColor, // 使用 VitePress 品牌色
    lang: navigator.language.toLowerCase(),
    moreVideoAttr: {
      crossOrigin: 'anonymous',
    },
  })
})

onBeforeUnmount(() => {
  if (art && art.destroy) {
    art.destroy(false)
  }
})
</script>

<style scoped>
.art-player-container {
  width: 100%;
  aspect-ratio: 16 / 9;
  border-radius: 8px;
  overflow: hidden;
  margin: 20px 0;
}
</style>

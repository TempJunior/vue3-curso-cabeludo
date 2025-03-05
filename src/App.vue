<template>
<BannerPika/>
<MainContent/>

</template>

<style scoped>

</style>

<script lang="ts">
import BannerPika from '@/components/BannerPika.vue'
import MainContent from '@/components/MainContent.vue'

export default {
  components: {
    MainContent,
    BannerPika
  }
}
</script>
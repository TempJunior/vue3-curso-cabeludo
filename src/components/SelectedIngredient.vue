<script lang="ts">
import TagComponent from '@/components/TagComponent.vue'

export default {
  components: { TagComponent },
  props: {
    ingrediente: { type: String, required: true },
  }
}
</script>

<template>
  <TagComponent :text="ingrediente" />
</template>

<style scoped></style>
<template>
  <div class="about">
    <h1>This is an about page</h1>
    <PartFile parent="About">About page</PartFile>
  </div>
</template>

<script>
// @ is an alias to /src
import PartFile from '@/components/PartFile.vue'

export default {
  name: 'AboutView',
  components: {
    PartFile,
  }
}
</script>
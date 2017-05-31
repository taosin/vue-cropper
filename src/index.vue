<template>
  <div>
  <upload :id="upload"></upload>
  </div>
</template>

<script>
  import upload from './components/upload'
  export default {
    components: {
      upload
    },
    data () {
      return {
        upload: 'upload'
      }
    },
    mounted () {
    }
  }
</script>

<style scoped>
</style>

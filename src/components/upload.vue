<template>
  <div class="v-upload">
    <div>
      <img id="image" src="https://odum9helk.qnssl.com/resource/gogopher.jpg">
    </div>
  </div>
</template>

<script>
  import $ from 'jquery'
  require('./../../static/cropper.min.js')
  require('./../../static/cropper.min.css')
  export default {
    name: 'upload',
    data () {
      return {
      }
    },
    mounted () {
      $('#image').cropper({
        aspectRatio: 16 / 9,
        crop (e) {
          console.log(e.x)
          console.log(e.y)
          console.log(e.width)
          console.log(e.height)
          console.log(e.rotate)
          console.log(e.scaleX)
          console.log(e.scaleY)
        }
      })
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>

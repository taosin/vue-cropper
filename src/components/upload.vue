<template>
  <div class="v-upload" >
    <div v-if="show">
      <img id="image" :src="img">
    </div>
    <div>
      <input type="file" :id="id" @change="change">
      <button @click="show=!show">{{show?'隐藏':'显示'}}</button>
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
        img: 'https://odum9helk.qnssl.com/resource/gogopher.jpg',
        show: false
      }
    },
    props: ['id'],
    mounted () {
      this.initCropper()
    },
    watch: {
      show (val) {
        if (val) {
          this.initCropper()
        }
      }
    },
    methods: {
      change () {
        const self = this
        const upload = document.getElementById('upload').files[0]
        if (upload) {
          self.img = window.URL.createObjectURL(upload)
          self.show = true
          $('#image').src = self.img
          self.initCropper()
        }
      },
      initCropper () {
        $('#image').cropper({
          aspectRatio: 1 / 1,
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

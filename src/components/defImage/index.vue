<template>
  <div>
    <img class="img"
         :src="imgUrl" />
  </div>

</template>

<script>
const DefPath = process.env.NODE_ENV === "production" ? imageDefUrl : ''

export default {
  props: {
    src: {
      type: String,
      require: true
    }
  },
  computed: {
    imgUrl() {
      if (DefPath) return this.src.replace(/^\/src\/images/, DefPath)
      else {
        let idx = this.src.indexOf('images')
        if (idx == -1) return ''
        let fileName = this.src.substr(idx + 7)
        return require(`../../images/${fileName}`)
      }
      
    }
  }
}
</script>

<style lang="scss" scoped>
.img {
  width: 100%;
  display: block;
}
</style>
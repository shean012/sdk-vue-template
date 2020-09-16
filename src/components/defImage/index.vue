<template>
  <div>
    <img class="image"
         :src="imgUrl" />
  </div>

</template>

<script>
const DefPath = process.env.NODE_ENV === 'production' ? imageDefUrl : ''

export default {
  props: {
    src: {
      type: String,
      require: true,
    },
  },
  computed: {
    imgUrl() {
      let idx = this.src.indexOf('images')
      if (idx == -1) return this.src
      let fileName = this.src.substr(idx + 7)
      if (DefPath) {
        return `${DefPath}${fileName}`
      } else {
        return require(`../../images/${fileName}`)
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.image {
  width: 100%;
  display: block;
}
</style>
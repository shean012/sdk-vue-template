<template>
  <div class="mainContainer">
    <div style="padding-top: 100px; text-align: center;">{{msg}}</div>
    <div style="width: 30%; margin: 0 auto; padding-top: 20px">
      <Images src="../images/vue.jpeg" />
    </div>
    <div v-for="(item, index) of images"
         :key="index">
      <div>{{item.name}}</div>
      <div style="width: 50px; background: #000">
        <Images :src="item.url" />
      </div>
    </div>
  </div>
</template>

<script>
import iconUrl from '../images/iowe.png'

export default {
  data() {
    return {
      msg: 'hello! Wellcome to dn vue project',
      images: [
        { name: 12, url: '../images/vue.jpeg' },
        { name: '23444', url: iconUrl },
        { name: '121233', url: iconUrl },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
</style>

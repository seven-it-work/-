<template>
<div>
  <el-input v-model:value="text"></el-input>
  <el-button @click="doIt">解析</el-button>
</div>
</template>

<script>
// import {Base64} from 'js-base64'

export default {
  data() {
    return {
      text: ''
    }
  },
  methods: {
    doIt() {
      let json = JSON.parse(this.text)
      this.$store.commit('setGameData', json)
      this.$router.push('Home')
    }
    // getUploadFile(file) {
    //   let fileReader = new FileReader()
    //   fileReader.readAsText(file)
    //   fileReader.onload = e => this.decodeData(fileReader.result)
    //   return false
    // },
    // decodeData(text) {
    //   let key = ['k', 'e', 'y']
    //   let result = Base64.decode(text)
    //     .split('')
    //     .map(c => c.charCodeAt(0))
    //   for (let i = 0; i < result.length; i++) {
    //     result[i] = result[i] ^ key[i % key.length].charCodeAt(0)
    //   }
    //   let json = JSON.parse(String.fromCharCode(...result))
    //
    //   this.$store.commit('setGameData', json)
    //   this.$router.push('Home')
    // }
  }
}
</script>

<style scoped>

</style>

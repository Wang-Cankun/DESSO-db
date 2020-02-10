<template>
  <div class="about">
    <span v-html="mdText"></span>
  </div>
</template>

<script>
//import helpData from '@/data/README.md'
let marked = require('marked')
import helloworld from 'raw-loader!@/data/README.md'
//let md = require('markdown-it')()
//const readmePath = require('@/data/README.md')
export default {
  name: 'Help',
  data() {
    return {
      mdText: String
    }
  },
  created() {
    //this.mdText = md.renderInline('__markdown-it__ rulezz!')
    //this.mdText = md.renderInline()
    this.mdText = marked(helloworld)
  }
}
</script>

<style lang="scss" scoped></style>

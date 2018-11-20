<template>
  <div class="hello">
      446466
       <div id="editorElem" style="text-align:left"></div>
        <button v-on:click="getContent">查看内容</button>
  </div>
</template>

<script>
import E from 'wangeditor'
export default {
      name: 'editor',
      data () {
        return {
          editorContent: ''
        }
      },

      methods: {
        getContent: function () {
            console.log(this.editorContent)
        }
      },

      mounted() {
        var editor = new E('#editorElem')
        editor.customConfig.uploadImgServer = 'www.baidu.com'//配置服务器端地址
        editor.customConfig.onchange = (html)=>{
          this.editorContent = html
        }
        editor.create()
      }


    }
</script>


<style scoped>

</style>

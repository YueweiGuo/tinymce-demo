<template>
  <div class="hello">
    <Editor id="tinymce" v-model="tinymceHtml" :init="editorInit" style="width: 900px;height: 500px;">
    </Editor>

    <div class="button" @click="submit">提交</div>
  </div>
</template>

<script>
import tinymce from 'tinymce/tinymce'
import 'tinymce/themes/silver/theme'
import Editor from '@tinymce/tinymce-vue'
import 'tinymce/plugins/image'
import 'tinymce/plugins/link'
import 'tinymce/plugins/code'
import 'tinymce/plugins/table'
import 'tinymce/plugins/lists'
import 'tinymce/plugins/contextmenu'
import 'tinymce/plugins/wordcount'
import 'tinymce/plugins/colorpicker'
import 'tinymce/plugins/textcolor'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: { Editor },
  mounted() {
    tinymce.init({})
  },
  data() {
    return {
      tinymceHtml: '11111111111111',
      editorInit: {
        language_url: '/tinymce/zh_CN.js',
        language: 'zh_CN',
        skin_url: '/tinymce/skins/ui/oxide',
        content_css: '/tinymce/skins/content/default/content.css',
        // plugins: 'link lists image code table colorpicker textcolor wordcount contextmenu',
        // toolbar:'bold italic underline strikethrough | fontsizeselect | forecolor backcolor | alignleft aligncenter alignright alignjustify | bullist numlist | outdent indent blockquote | undo redo | link unlink image code | removeformat',
        // branding: false
      }
    }
  },
  methods: {
    submit() {
      console.log(this.tinymceHtml)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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

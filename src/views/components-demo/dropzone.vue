<template>
  <div class="components-container">
    <aside>
      基于 <a class="link-type" href="https://github.com/rowanwins/vue-dropzone"> dropzone </a>.
      因为我的业务有特殊需求，需要上传图片到qiniu，所以我选择自己封装，而不是第三方。它非常简单，您可以在@/components/Dropzone中看到详细代码。
    </aside>
    <div class="editor-container">
      <dropzone id="myVueDropzone" url="https://httpbin.org/post" @dropzone-removedFile="dropzoneR" @dropzone-success="dropzoneS" />
    </div>
  </div>
</template>

<script>
import Dropzone from '@/components/Dropzone'

export default {
  name: 'DropzoneDemo',
  components: { Dropzone },
  methods: {
    dropzoneS(file) {
      console.log(file)
      this.$message({ message: 'Upload success', type: 'success' })
    },
    dropzoneR(file) {
      console.log(file)
      this.$message({ message: 'Delete success', type: 'success' })
    }
  }
}
</script>


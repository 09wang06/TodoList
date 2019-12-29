<template>
  <li @click="HistroyClick">
    {{content}}
  </li>
</template>

<script>
  export default{
    props:['content','index'],
    methods:{
      HistroyClick() {
        alert("---第"+(this.index+1)+"条记录已被删除！--")
        this.$emit('delete', this.index);
      }
    }
  }

</script>

<!--样式表部分-->
<style scoped>


</style>

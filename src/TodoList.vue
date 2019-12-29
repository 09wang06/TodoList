<template>
  <div >
    <div>
      <input v-model="inputValue"/>
      <button @click="HandSubmit">提交</button>
    </div>
    <ul>
      <todo-item
        v-for="(item, index ) of list"
        :key="index"
        :content="item"
        :index="index"
        @delete="HistroyDelete"
      >
        
      </todo-item>
      
    </ul>
  </div>
</template>

<script>
  import TodoItem from './components/TodoItem'
  export default {
    components:{
      'todo-item':TodoItem,
    },
    data () {   //相当于 data:function(){
      return {
        inputValue:'',
        list: [],
      }
    },
    methods:{
      HandSubmit () {
        this.list.push(this.inputValue);  //this.$emit.list.push()
        this.inputValue='';
      },
      HistroyDelete(index){
        this.list.splice(index, 1)
      }
    }
  }
</script>

<style>

</style>

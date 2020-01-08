<template>
  <div>
    <input v-model="inputValue"/>
    <button @click="handleSubmit">提交</button>
    <ul>
      <todoitem v-for="(item, index) of list" :key="index" :content="item" :index="index" @deleteItem="handleDelete">
      </todoitem>
    </ul>
  </div>
</template>

<script>
import todoitem from './components/TodoItem'
export default {
  components: {
    todoitem
  },
  data () {
    return {
      inputValue: '',
      list: ['1', '2', '3']
    }
  },
  methods: {
    handleSubmit () {
      if (this.inputValue !== '') {
        this.list.push(this.inputValue)
        this.inputValue = ''
      }
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>

</style>

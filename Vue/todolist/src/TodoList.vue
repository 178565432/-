<template>
  <div>
  <div>
    <label>
      <input v-model="inputValue"/>
    </label>
    <button @click="handleSubmit">提交</button>
  </div>
  <ul>
    <todo-item
      v-for="(item,index) of list "
      :key="index"
      :content="item"
      :index="index"
      @delete="handleDelete"
      ></todo-item>
  </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  comments: {
    'todo-item': TodoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit: function () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }

}
</script>

<style>

</style>

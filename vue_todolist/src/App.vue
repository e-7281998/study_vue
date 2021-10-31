<template lang="html">
  <div id="app">
    <todoHeader></todoHeader>
    <todoInput></todoInput>
    <todoList></todoList>
    <todoFooter></todoFooter>
  </div>
</template>

<script>
import todoHeader from './components/todoHeader'
import todoInput from './components/todoInput'
import todoList from './components/todoList'
import todoFooter from './components/todoFooter'

export default {
  components: {
    'todoHeader': todoHeader,
    'todoInput': todoInput,
    'todoList': todoList,
    'todoFooter': todoFooter
  }
}
</script>

<style lang="css" scoped>
</style>

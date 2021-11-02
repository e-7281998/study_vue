<template lang="html">
  <div id="app">
    <todoHeader></todoHeader>
    <todoInput v-on:addTodo="addTodo"></todoInput>
    <todoList v-bind:propsdata="todoItems" @removeTodo="removeTodo"></todoList>
    <todoFooter v-on:removeAll="clearAll"></todoFooter>
  </div>
</template>

<script>
import todoHeader from './components/todoHeader'
import todoInput from './components/todoInput'
import todoList from './components/todoList'
import todoFooter from './components/todoFooter'

export default {
  data(){
    return {
      todoItems: []
    }
  },
  created(){
    if(localStorage.length > 0){
      for(var i=0; i < localStorage.length; i++){
        this.todoItems.push(localStorage.key(i));
      }
    }
  },
  methods: {
    addTodo(todoItem){
      ﻿localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    },
    removeTodo(todoItem, index){
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index, 1);
    },
    clearAll(){
      localStorage.clear();
      this.todoItems = [];
    }
  },
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

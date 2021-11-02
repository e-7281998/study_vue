<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" placeholder="Type what you have to do">
    <span class="addContainer" v-on:click="addTodo">
      <i  class="fa fa-plus" aria-hidden="true"></i>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodo(){
      if(this.newTodoItem !== ''){
        //인풋박스에 입력된 텍스트의 앞뒤 공백 문자열 제거하기
        var value = this.newTodoItem && this.newTodoItem.trim();
        //value: 이벤트 전달할 때 할 일 텍스트 값
        this.$emit('addTodo', value);
        this.clearInput();
      }
    },
    clearInput(){
      this.newTodoItem = '';
    }
  }
}
</script>

<style scoped>
  input:focus {
    outline: none;
  }
  .inputBox {
    background: #fff;
    height: 50px;
    line-height: 50px;
    border-radius: 5px;
  }
  .inputBox input {
    border-style: none;
    font-size: 0.9rem;
  }
  .addContainer {
    display: inline-block;
    float: right;
    background: linear-gradient(to right, #6478fb, #8763fb);
    width: 3rem;
    border-radius: 0 5px 5px 0;
    color: #fff;
  }
  .addBtn {
    color: #fff;
    vertical-align: middle;
  }
</style>

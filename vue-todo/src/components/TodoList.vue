<template>
  <div>
    <ul>
      <li v-for="todoItem in todoItems" :key="todoItem">
        {{ todoItem }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      todoItems: []
    }
  },
  created: function() { // 인스턴스 생성 직후의 hook
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== 'loglevel:webpack-dev-server') {
          this.todoItems.push(localStorage.key(i));
        }
      }
    }
  },
  mounted: function() {

  }
}
</script>

<style>

</style>
<template>
 <div>
  <button @cliсk="emitToapp" class="enter-btn">
   Вход
  </button>
 </div>
</template>

<script>

export default {
 data() {
  return {
   isAuth: false
  }
 },
 methods: {
  emitToapp() {
   this.isAuth = true;
   this.$emit('click', this.isAuth);
  }
 }
}
</script>

<style scoped>
.enter-btn {
 width: 20rem;
 height: 6rem;
 background: #9db2df;
 font-size: 2rem;
 cursor: pointer;
}
</style>
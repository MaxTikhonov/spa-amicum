<template>
 <div class="wrapper">
  <div class="data-and-enter">
   <current-data></current-data>
   <div class="enter">
    <enter-and-out @emited-from-enterandout="emitedFromEnterAndOut">Выход</enter-and-out>
   </div>
  </div>
  <div class='for-togle'>
   <togle></togle>
  </div>
  <user-view />
  <wrapper-for-sidebar-block />
 </div>
</template>

<script>
import UserView from './UserView.vue';
import WrapperForSidebarBlock from './WrapperForSidebarBlock/WrapperForSidebarBlock.vue';
export default {
 emits: ["updatedcount"],
 components: {
  UserView,
  WrapperForSidebarBlock
 },
 data() {
  return {
   isAuthOut: true
  }
 },
 watch: {
  isAuthOut(newValue, oldValue) {
   if (newValue == false) {
    this.emitToApp(newValue);
   }
   else {
   }
  }
 },
 methods: {
  emitedFromEnterAndOut(event) {
   this.isAuthOut = event;
  },
  emitToApp(event) {
   this.$emit('emited-from-sidebar', event)
  }
 }
}
</script>

<style scoped>
.wrapper {
 display: flex;
 flex-direction: column;
 background: #323a53;
}

.data-and-enter {
 display: flex;
 justify-content: space-between;
 color: #fff;
 font-size: 1.5rem;
}

.enter {
 width: 7.3rem;
 display: flex;
 align-items: center;
 justify-content: space-between;
}

.for-togle {
 display: flex;
 justify-content: flex-end;
}
</style>
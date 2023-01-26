<template>
 <slot></slot>
 <div><image-icon @emited-auth="emitedFromImageIcon"></image-icon></div>
</template>

<script>

export default {
 name: 'enter-and-out',
 emits: ["updatedcount"],
 data() {
  return {
   isAuthOut: true
  }
 },
 watch: {
  isAuthOut(newValue, oldValue) {
   if (newValue == false) {
    this.$emit('emited-from-enterandout', newValue);
   }
   else {
   }
  }
 },
 methods: {
  emitedFromImageIcon(event) {
   this.isAuthOut = event;
   console.log(this.isAuthOut)
  },
  // emitToSIdebar(event) {
  //  console.log(event)
  //  this.$emit('emited-enterandout', event)
  // }
 }
}
</script>

<style scoped>

</style>
<template>
 <div class="img" @click="exportEventOfOuting">
  <img src="./enter.jpg" />
 </div>
</template>

<script>

export default {
 name: 'image-icon',
 emits: ["updatedcount"],
 props: {
  srcOfImage: ''
 },
 data() {
  return {
   isAuthOut: true
  }
 },
 methods: {
  exportEventOfOuting() {
   this.isAuthOut = false;
   this.$emit('emited-auth', false)
  }
 }
}
</script>

<style>
.img {
 display: flex;
 align-items: center;
 width: 2.5rem;
 height: 2.5rem;
}

.img:hover {
 cursor: pointer;
}

img:active {
 width: 2.1rem;
 height: 2.1rem;
}
</style>
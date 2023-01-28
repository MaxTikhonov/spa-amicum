<template>
 <div class="wrapper-column" style="align-items: center;" @click="exportEventOfOuting">
  <div v-if="text">{{ text }}</div>
  <img class="img" :src="src" alt="">
 </div>
</template>

<script>

export default {
 name: 'image-icon',
 emits: ["updatedcount"],
 props: {
  infoForImage: {
   type: Object,
   required: true
  },
 },
 data() {
  return {
   isAuthOut: true,
   src: '',
   width: '',
   height: '',
   margin: '',
   text: ''
  }
 },
 methods: {
  exportEventOfOuting() {
   this.isAuthOut = false;
   this.$emit('emited-auth', false)
  },
  getSrcOfImage() {
   this.text = this.infoForImage.text;
   this.fontSize = this.infoForImage.fontSize;
   this.src = this.infoForImage.srcOfImage;
   this.width = this.infoForImage.width;
   this.height = this.infoForImage.height;
   this.margin = this.infoForImage.margin;
   this.fontSize = this.infoForImage.fontSize;
  }
 },
 mounted() {
  this.getSrcOfImage();
 }
}
</script>

<style>
.img {
 width: v-bind(width);
 height: v-bind(height);
 margin: v-bind(margin);
}

.wrapper-column {
 font-size: v-bind(fontSize);
}

.img:hover {
 box-sizing: border-box;
 cursor: pointer;
}

img:active {
 border: .2rem solid #fff;
 border-radius: .2rem;
}
</style>
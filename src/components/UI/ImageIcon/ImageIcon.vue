<template>
 <div class="wrapper-column" style="align-items: center;" @click="exportEventOfOuting">
  <div v-if="text">{{ text }}</div>
  <img v-if="showFavicon" class="img" :src="src" alt="">
  <div v-if="showCounter">
   <auto-filling-counter>
   </auto-filling-counter>
  </div>
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
   showCounter: false,
   showFavicon: false,
   isAuthOut: true,
   src: '',
   width: '',
   height: '',
   margin: '',
   text: '',
   border: '4px solid #fff',
   borderRadius: '',
   progress: '',
   progressOfDays: ''
  }
 },
 methods: {
  exportEventOfOuting() {
   this.isAuthOut = false;
   this.$emit('emited-auth', false)
  },
  getSrcOfImage() {
   this.progressOfDays = this.infoForImage.progressOfDays;
   this.showCounter = this.infoForImage.showCounter;
   this.showFavicon = this.infoForImage.showFavicon;
   this.border = this.infoForImage.border;
   this.borderRadius = this.infoForImage.borderRadius;
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
 border: v-bind(border);
 border-radius: v-bind(borderRadius);
}

.wrapper-column {
 font-size: v-bind(fontSize);
}

.img:hover {
 box-sizing: border-box;
 cursor: pointer;
}
</style>
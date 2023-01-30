<template>
 <div class="wrapper-column" style="align-items: center; justify-content: space-between;" @click="exportEventOfOuting">
  <div v-if="text" style="margin: 1rem; text-align: center;" class="text">{{ text }}</div>
  <img v-if="showFavicon" class="img" :src="src" alt="">
  <div v-if="showCounter">
   <auto-filling-counter :infoForImage="infoForImage" />
  </div>
 </div>
</template>

<script>
import AutoFillingCounter from '../AutoFillingCounter.vue';

export default {
 components: {
  AutoFillingCounter
 },
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
   progressOfDays: '',
   fontSizeForAutoFillingText: '',
   heightOfWrapper: '',
   backGround: ''
  }
 },
 methods: {
  exportEventOfOuting() {
   this.isAuthOut = false;
   this.$emit('emited-auth', false)
  },
  getSrcOfImage() {
   this.backGround = this.infoForImage.backGround;
   this.heightOfWrapper = this.infoForImage.heightOfWrapper;
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

<style scoped>
.img {
 width: v-bind(width);
 height: v-bind(height);
 margin: v-bind(margin);
 border: v-bind(border);
 border-radius: v-bind(borderRadius);
}

.wrapper-column {
 display: flex;
 flex-direction: column;
 height: v-bind(heightOfWrapper);
 font-size: v-bind(fontSize);
}

.img:hover {
 box-sizing: border-box;
 cursor: pointer;
}
</style>
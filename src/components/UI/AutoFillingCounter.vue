<template>
 <div class="wrapper">
  <div class="timer">
   <div class="timer-line">
   </div>
   <div class="timer-body cntr-wrapper">
    <img v-if="infoForImage.srcOfImage" :src="infoForImage.srcOfImage" alt="" class="img">
    <div>
     <div v-if="infoForImage.progressOfDays" class="days">{{ infoForImage.progressOfDays }}</div>
     <div v-if="infoForImage.wordOfDay">{{ infoForImage.wordOfDay }}</div>
    </div>
    <div class="timer-counter"></div>
   </div>
  </div>
 </div>
</template>

<script>

export default {
 name: 'auto-filling-counter',
 props: {
  infoForImage: {
   type: Object,
   required: true
  },
 },
 data() {
  return {
   srcOfImage: '',
   width: '',
   height: '',
   fontSizeForAutoFillingText: ''
  }
 },
 methods: {
  getImage() {
   this.width = this.infoForImage.width;
   this.height = this.infoForImage.height;
   this.fontSizeForAutoFillingText = this.infoForImage.fontSizeForAutoFillingText;
  }
 },
 mounted() {
  this.getImage();
 }

}
</script >

<style scoped>
.wrapper {
 min-height: 100%;
 display: flex;
 justify-content: center;
 align-items: center;
}

.cntr-wrapper {
 display: flex;
 justify-content: center;
 align-items: center;
}

.days {
 font-size: v-bind(fontSizeForAutoFillingText);
}

.img {
 width: v-bind(width);
 height: v-bind(height);
}

.timer {
 width: 100px;
 height: 100px;
 border-radius: 50%;
 display: flex;
 justify-content: center;
 align-items: center;
 overflow: hidden;
 position: relative;
}

.timer-line {
 position: absolute;
 top: 0;
 left: 0;
 width: 100%;
 height: 100%;
 z-index: 2;
 animation: line 4s linear forwards;
}

.timer:before {
 content: '';
 position: absolute;
 top: 0;
 left: 0;
 width: 50%;
 height: 100%;
 z-index: 3;
 background-color: #596c94;
 animation: mask-left 4s steps(1, end) forwards;
}

.timer:after {
 content: '';
 position: absolute;
 top: 0;
 right: 0;
 width: 50%;
 height: 100%;
 z-index: 3;
 background-color: #16e050;
 animation: mask-right 4s steps(1, end) forwards;
}

.timer-body {
 width: 80px;
 height: 80px;
 border-radius: 50%;
 background-color: #596c94;
 text-align: center;
 overflow: hidden;
 z-index: 4;
}

.timer-line:after {
 content: '';
 position: absolute;
 top: 0;
 left: 0;
 width: 50%;
 height: 100%;
 background-color: #16e050;
}

@keyframes line {
 0% {}

 100% {
  transform: rotate(360deg);
 }
}

@keyframes mask-left {
 0% {
  visibility: visible;
 }

 50%,
 100% {
  visibility: hidden;
 }

}

@keyframes mask-right {
 0% {
  visibility: hidden;
 }

 50%,
 100% {
  visibility: visible;
 }

}
</style>

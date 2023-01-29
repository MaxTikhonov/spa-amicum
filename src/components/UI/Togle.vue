<template>
 <div class="wrapper">
  <div class="area dark-theme-middlebluebg">
   <transition name="fade" class="absolute" style="bottom: -1.35rem; left: -1.3rem; z-index: 1;">
    <image-icon @click="switchTogle" v-if="showSun" :infoForImage="infoForImage"></image-icon>
   </transition>
   <transition name="fade" class="absolute" style="top: -1.4rem; right: -1.95rem; z-index: 1;">
    <image-icon @click="switchTogle" v-if="showMoon" :infoForImage="infoForImage2"></image-icon>
   </transition>
   <div class="wrapper-row" style="justify-content: space-between;">
    <div class="mover light-themebg"></div>
    <div class="reversemover dark-themebg"></div>
   </div>
  </div>
 </div>
</template>

<script>

export default {
 name: 'togle',
 data() {
  return {
   showSun: true,
   showMoon: false,
   mover: {},
   reverseMover: {},
   infoForImage: {
    showFavicon: true,
    srcOfImage: 'https://img.icons8.com/ios-glyphs/60/FFFFFF/sun--v1.png',
    width: '4rem',
    height: '4rem'
   },
   infoForImage2: {
    showFavicon: true,
    srcOfImage: 'https://img.icons8.com/external-others-aquariid/64/000000/external-climate-weather-others-aquariid-116.png',
    width: '4.2rem',
    height: '4.2rem'
   }
  }
 },
 methods: {
  switchTogle() {
   if (this.showSun == true) {
    this.showSun = false;
    this.showMoon = true;
    this.mover.classList.add('mover2');
    setTimeout(() => this.reverseMover.classList.remove('mover3'), 10);
   }
   else {
    this.showSun = true;
    this.showMoon = false;
    this.reverseMover.classList.add('mover3');
    setTimeout(() => this.mover.classList.remove('mover2'), 10);

   }
  },
  getMover() {
   this.mover = document.querySelector('.mover');
  },
  getReverseMover() {
   this.reverseMover = document.querySelector('.reversemover');
  }
 },
 mounted() {
  this.getMover();
  this.getReverseMover();
 }
}
</script>

<style scoped>
.absolute {
 position: absolute;
}

.wrapper {
 margin: 4rem 0rem 4rem 0rem;
 color: #fff;
 font-size: 2rem;
}

.mover {
 width: 1.3rem;
 height: 1.3rem;
 border-radius: 50%;
}

.reversemover {
 width: 1.3rem;
 height: 1.3rem;
 border-radius: 50%;
 margin-left: 2rem;
 z-index: 0;
 opacity: 0;
}

.area {
 position: relative;
 width: 5rem;
 margin: 0 auto;
 border-radius: 50px;
}

.mover2 {
 animation: move .5s linear alternate 1 forwards;
}

.mover3 {
 animation: move3 .5s linear alternate 1 forwards;
}

@keyframes move2 {
 100% {
  transform: translate(-3rem, 0);
  background: #FFFFFF;
 }
}

@keyframes move {
 15% {
  background: #ededed;
 }

 30% {
  background: #c8c8c8;
 }

 50% {
  background: #b5b5b5;
 }

 65% {
  background: #9f9f9f;
 }

 70% {
  background: #8e8e8e;
 }

 75% {
  background: #7d7d7d;
 }

 80% {
  background: #666666;
 }

 85% {
  background: #555555;
 }

 90% {
  background: #454545;
 }

 95% {
  background: #1c1c1c;
 }

 99.9% {
  transform: translate(3.8rem, 0);
  background: #000000;
 }

 100% {
  opacity: 0;
 }
}

@keyframes move3 {
 0% {
  opacity: 1;
 }

 15% {
  background: #1c1c1c;
 }

 30% {
  background: #1c1c1c;

 }

 50% {
  background: #454545;
 }

 65% {
  background: #555555;
 }

 70% {
  background: #666666;
 }

 75% {
  background: #8e8e8e;
 }

 80% {
  background: #9f9f9f;
 }

 85% {
  background: #b5b5b5;
 }

 90% {
  background: #c8c8c8;
 }

 95% {
  background: #ededed;

 }

 99.9% {
  transform: translate(-3.8rem, 0);
  background: #FFFFFF;
  opacity: 1;
 }

 100% {
  opacity: 0;
 }
}


.fade-enter-from {
 opacity: 0;
}

.fade-enter-to {
 opacity: 1;
}

.fade-enter-active {
 transition: all .25s ease;
}

.fade-leave-from {
 opacity: 1;
}

.fade-leave-to {
 opacity: 0;
}

.fade-leave-active {
 transition: all .25s ease;
}
</style>
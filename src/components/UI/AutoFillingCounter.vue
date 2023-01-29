<template>
 <div class="circle">
  <div class="circle__item">
   <div class="circle__half circle__half--clipped"></div>
  </div>
  <div class="circle__half circle__half--fix">
  </div>
 </div>
</template>

<script>

export default {
 name: 'auto-filling-counter'
}
</script>

<style>
.circle {
 position: relative;
 width: 6rem;
 height: 6rem;
 background: #ccc;
 border-radius: 100%;
}

.circle__item {
 width: 50%;
 height: 100%;
 right: 0px;
 position: absolute;
 overflow: hidden;
 transform-origin: left center;
}

.circle .circle__item {
 animation: anim1 6s 1;
 transform: rotate(180deg);
}

@keyframes anim1 {
 0% {
  transform: rotate(0deg);
 }

 50% {
  transform: rotate(0deg);
 }

 50.01% {
  transform: rotate(180deg);
 }

 100% {
  transform: rotate(180deg);
 }
}

.circle__half {
 height: 100%;
 right: 0px;
 position: absolute;
 border: solid 10px transparent;
 border-top-color: green;
 border-left-color: green;
 border-radius: 50%;
}

.circle__half--clipped {
 width: 200%;
 transform: rotate(-45deg);
}

.circle .circle__half--clipped {
 transform: rotate(135deg);
 animation: anim2 3s linear 2;
}

@keyframes anim2 {
 0% {
  transform: rotate(-45deg);
 }

 100% {
  transform: rotate(135deg);
 }
}

.circle__half--fix {
 width: 100%;
 transform: rotate(135deg);
 opacity: 0;
}

.circle:hover .circle__half--fix {
 opacity: 1;
 animation: anim3 6s 1;
}

@keyframes anim3 {
 0% {
  opacity: 0;
 }

 49.99% {
  opacity: 0;
 }

 50% {
  opacity: 1;
 }

 100% {
  opacity: 1;
 }
}
</style>

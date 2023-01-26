<template>
 <div class="wrapper" v-bind="currentData">
  <div>
   <span>{{ currentData.date }}</span>
  </div>
  <div>
   <span>{{ currentData.time }}</span>
  </div>
 </div>
</template>

<script>

export default {
 name: 'current-data',
 data() {
  return {
   currentData: {
    date: '',
    time: ''
   },
   interval: 0,
   interval2: 0,
  }
 },
 methods: {
  getCurrentData() {
   const date = new Date().toLocaleDateString().replaceAll("/", '.');
   let a = [];
   a = date.split('.');
   a.forEach(function (elem, index) {
    +elem < 10 ? a[index] = (`0${elem}`) : a[index] = elem;
   })
   let c = a.join('.');
   this.currentData.date = c;
  },
  getCurrentTime() {
   const time = new Date().toLocaleTimeString().slice(0, -6);
   this.currentData.time = time;
  },
  startTimer() {
   this.stopTimer()
   this.interval = window.setInterval(() => {
    this.getCurrentTime()
   }, 1000)
   this.interval2 = window.setInterval(() => {
    this.getCurrentData()
   }, 1000)
  },
  stopTimer() {
   if (this.interval) {
    window.clearInterval(this.interval)
   }
   if (this.interval2) {
    window.clearInterval(this.interval2)
   }
  }
 },
 mounted() {
  this.startTimer()
 },
 beforeDestroy() {
  this.stopTimer()
 }
} 
</script>

<style scoped>
.wrapper {
 display: flex;
 flex-direction: column;
 color: #fff;
 font-family: Roboto sans-serif;
 font-size: 1.5rem;
}
</style>
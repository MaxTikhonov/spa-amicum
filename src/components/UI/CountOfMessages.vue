<template>
 <div class="outer-circle">
  <div class="inner-div">{{ infoOfMessages.amountOfMessages }}
  </div>
 </div>
</template>

<script>

export default {
 props: {
  infoOfMessages: {
   type: Object,
   required: true
  },
 },
 data() {
  return {
   amountOfMessages: '',
   width: '',
   height: '',
   fontSize: '',
   backGround: ''
  }
 },
 methods: {
  getInfoOfMessages() {
   this.amountOfMessages = this.infoOfMessages.amountOfMessages;
   this.width = this.infoOfMessages.width;
   this.height = this.infoOfMessages.height;
   this.fontSize = this.infoOfMessages.fontSize;
   this.backGround = this.infoOfMessages.backGround;
  }
 },
 mounted() {
  this.getInfoOfMessages();
 }
}
</script>

<style scoped>
.outer-circle {
 display: flex;
 justify-content: center;
 align-items: center;
 width: v-bind(width);
 height: v-bind(height);
 font-size: v-bind(fontSize);
 background: v-bind(backGround);
 border-radius: 50%;
}
</style>

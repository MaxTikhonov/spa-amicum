<template>
 <div class="wrapper">
  <div class="data-and-enter">
   <current-data></current-data>
   <div class="enter">
    <enter-and-out>Выход</enter-and-out>
   </div>
  </div>
 </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.wrapper {
 display: flex;
 flex-direction: column;
 background: #323a53;
}

.data-and-enter {
 display: flex;
 justify-content: space-between;
 color: #fff;
 font-size: 1.5rem;
}

.enter {
 width: 7.3rem;
 display: flex;
 align-items: center;
 justify-content: space-between;
}
</style>
<template>
 <div class="flex-wrap" style="justify-content: center; margin: 0rem -1rem;">
  <div v-for="infoForImage in arrayOfImageObjects" class="dark-theme-middlebluebg white-color"
   style="width: 15rem; margin: 1rem;">
   <image-icon :infoForImage="infoForImage">
   </image-icon>
  </div>
 </div>
</template>

<script>

export default {
 data() {
  return {
   arrayOfImageObjects: [
    {
     showFavicon: true,
     srcOfImage: 'https://img.icons8.com/external-solid-design-circle/64/FFFFFF/external-Hammer-carpenter-solid-design-circle.png',
     width: '3rem',
     height: '3rem',
     fontSize: '1.3rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Инструктаж',
     showCounter: true,
     progressOfDays: '12'
    },
    {
     showFavicon: true,
     srcOfImage: 'https://img.icons8.com/external-smashingstocks-glyph-smashing-stocks/66/FFFFFF/external-email-user-interface-smashingstocks-glyph-smashing-stocks.png',
     width: '3rem',
     height: '3rem',
     fontSize: '1.3rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Предсменный экзаменатор',
     showCounter: true,
     progressOfDays: '3'
    }
   ]
  }
 }
}
</script>

<style scoped>

</style>

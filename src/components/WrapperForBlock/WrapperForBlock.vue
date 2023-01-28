<template>
 <div style="margin: 6rem 0rem 0rem 12rem;">
  <div style="display: flex; flex-wrap: wrap;">
   <div v-for="infoForImage in arrayOfImageObjects">
    <div class="cntr-wrapper dark-theme block" style="border-radius: .4rem;"><image-icon
      :infoForImage="infoForImage"></image-icon></div>
   </div>
  </div>
 </div>
</template>

<script>

export default {
 data() {
  return {
   arrayOfImageObjects: [
    {
     srcOfImage: 'https://img.icons8.com/external-solid-design-circle/64/FFFFFF/external-Hammer-carpenter-solid-design-circle.png',
     width: '8rem',
     height: '8rem',
     fontSize: '2rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Начать работу'
    },
    {
     srcOfImage: 'https://img.icons8.com/external-smashingstocks-glyph-smashing-stocks/66/FFFFFF/external-email-user-interface-smashingstocks-glyph-smashing-stocks.png',
     width: '8rem',
     height: '8rem',
     fontSize: '2rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Уведомления'
    },
    {
     srcOfImage: 'https://img.icons8.com/ios-filled/50/FFFFFF/literature--v1.png',
     width: '8rem',
     height: '8rem',
     fontSize: '2rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Обучение'
    },
    {
     srcOfImage: 'https://img.icons8.com/external-tal-revivo-bold-tal-revivo/96/FFFFFF/external-star-medal-awarded-for-the-performance-in-army-rewards-bold-tal-revivo.png',
     width: '8rem',
     height: '8rem',
     fontSize: '2rem',
     margin: '1rem 0rem 0rem 0rem',
     text: 'Достижения'
    }
   ]
  }
 },
}
</script>

<style scoped>
.block {
 width: 24rem;
 height: 18rem;
 margin: 2.5rem;
}
</style>
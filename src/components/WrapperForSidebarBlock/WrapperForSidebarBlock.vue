<template>
 <div class="flex-wrap" style="justify-content: center; align-items: flex-end; margin: 0rem -1rem;">
  <div v-for="infoForImage in arrayOfImageObjects" class="dark-theme-middlebluebg white-color"
   style="width: 15rem; height: 15rem; margin: 1rem; border-radius: .2rem;">
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
     showFavicon: false,
     srcOfImage: 'https://img.icons8.com/ios/50/FFFFFF/test-results.png',
     width: '2.8rem',
     height: '2.8rem',
     fontSize: '1.3rem',
     margin: '',
     text: 'Инструктаж',
     showCounter: true,
     progressOfDays: '',
     heightOfWrapper: '13rem'
    },
    {
     showFavicon: false,
     srcOfImage: 'https://img.icons8.com/external-linector-lineal-linector/64/FFFFFF/external-exam-university-linector-lineal-linector.png',
     width: '2.8rem',
     height: '2.8rem',
     fontSize: '1.3rem',
     margin: '',
     text: 'Предсменный экзаменатор',
     showCounter: true,
     progressOfDays: '',
     heightOfWrapper: '13rem'
    },
    {
     showFavicon: false,
     srcOfImage: '',
     width: '2rem',
     height: '2rem',
     fontSize: '1.3rem',
     margin: '',
     text: 'Тестов выполнено',
     showCounter: true,
     progressOfDays: '12',
     fontSizeForAutoFillingText: '3rem',
     heightOfWrapper: '13rem'
    },
    {
     showFavicon: false,
     srcOfImage: '',
     width: '2rem',
     height: '2rem',
     fontSize: '1.3rem',
     margin: '',
     text: 'Аттестация через',
     showCounter: true,
     progressOfDays: '3',
     wordOfDay: 'дня',
     fontSizeForAutoFillingText: '2rem',
     heightOfWrapper: '13rem'
    },
   ]
  }
 }
}
</script>

<style scoped>

</style>

<template>
  <div style="margin: 6rem 0rem 0rem 12rem;">
    <div style="display: flex; flex-wrap: wrap;">
      <div v-for="(infoForImage, index) in arrayOfImageObjects">
        <div class="cntr-wrapper dark-theme-orangebg white-color block"
          style="border-radius: .4rem; position: relative;">
          <count-of-messages v-if="index == 1" class="count-of-messages" :infoOfMessages="infoOfMessages" /><image-icon
            :infoForImage="infoForImage" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CountOfMessages from '../UI/CountOfMessages.vue';
import ImageIcon from '../UI/ImageIcon/ImageIcon.vue';
export default {
  components: {
    CountOfMessages,
    ImageIcon
  },
  data() {
    return {
      arrayOfImageObjects: [
        {
          showFavicon: true,
          srcOfImage: 'https://img.icons8.com/external-solid-design-circle/64/FFFFFF/external-Hammer-carpenter-solid-design-circle.png',
          width: '8rem',
          height: '8rem',
          fontSize: '2rem',
          margin: '1rem 0rem 0rem 0rem',
          text: 'Начать работу',
          backGround: '#ef7f1b'
        },
        {
          showFavicon: true,
          srcOfImage: 'https://img.icons8.com/external-smashingstocks-glyph-smashing-stocks/66/FFFFFF/external-email-user-interface-smashingstocks-glyph-smashing-stocks.png',
          width: '8rem',
          height: '8rem',
          fontSize: '2rem',
          margin: '1rem 0rem 0rem 0rem',
          text: 'Уведомления',
          backGround: '#ef7f1b'
        },
        {
          showFavicon: true,
          srcOfImage: 'https://img.icons8.com/ios-filled/50/FFFFFF/literature--v1.png',
          width: '8rem',
          height: '8rem',
          fontSize: '2rem',
          margin: '1rem 0rem 0rem 0rem',
          text: 'Обучение',
          backGround: '#ef7f1b'
        },
        {
          showFavicon: true,
          srcOfImage: 'https://img.icons8.com/external-tal-revivo-bold-tal-revivo/96/FFFFFF/external-star-medal-awarded-for-the-performance-in-army-rewards-bold-tal-revivo.png',
          width: '8rem',
          height: '8rem',
          fontSize: '2rem',
          margin: '1rem 0rem 0rem 0rem',
          text: 'Достижения',
          backGround: '#ef7f1b'
        }
      ],
      infoOfMessages: {
        amountOfMessages: '2',
        width: '2.5rem',
        height: '2.5rem',
        fontSize: '1.5rem',
        backGround: '#16e050'
      }
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

.cntr-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}

.count-of-messages {
  position: absolute;
  top: -1.2rem;
  right: -1.2rem;
}

.white-color {
  color: #fff;
}

.dark-theme-orangebg {
  background: #ef7f1b;
}
</style>
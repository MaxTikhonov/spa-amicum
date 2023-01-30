<template>
  <div class="wrapper-for-enter" v-if="isAuth == false">
    <enter @click="emitedIsAuth" />
  </div>
  <div class="main" v-else="">
    <sidebar style="width: calc(100vw/10*2.8);
      padding: 2.3rem;
      border-top-right-radius: 1.5rem;
      border-bottom-right-radius: 1.5rem;" @emited-from-sidebar="changeIsAuth" />
    <div class="someclass">
      <div class="wrapper-row" style="justify-content: flex-end;">
        <image-icon :infoForImage="infoForImage" />
      </div>
      <div>
        <wrapper-for-block />
      </div>
    </div>
  </div>

</template>

<script>
import UserView from '@/components/UserView.vue'
import Sidebar from '@/components/Sidebar.vue'
import Enter from './components/Enter.vue'
import WrapperForBlock from './components/WrapperForMainBlock/WrapperForBlock.vue'
import ImageIcon from './components/UI/ImageIcon/ImageIcon.vue'

export default {
  components: {
    UserView,
    Sidebar,
    Enter,
    WrapperForBlock,
    ImageIcon
  },
  data() {
    return {
      infoForImage: {
        srcOfImage: 'https://lh3.googleusercontent.com/PwaIj9xoo5Ll7hS31butwn2gtAokb1wzs1uXXWTIYNeEp45t_P_JsDRBxkXoykiouJ_dFZIF9mp5h77vGsZylHL8XjUaeXM3akdTn_Lp4_uxQtYW67dvJws1iJNAz9_xBKOskoQj6uzaRLoZWDFYswkFAVscAPWwtA_b-1MhAg8D4fslCEbnZ6bc4unJ5DhstNohV0u5AziYOvi89rVchGPoRP9hDJ46n5LPxqXco8pDGBfg98Ocl4U3lslHBrl5LZJQj9_-FB7KRYrGswdDC6PKYl9DJJrliqv0tWrq-r_snIFeOhmZtjEipg7jfpIkdkUM_JM8XbBKbxLlueKm40-eE6sxNFuKmt1znt1baoprzBBH6J9M6tiJBEJYfll4SgWX6cv9CRDCDUMC9pB2VLmFDhiocsPdB9a7bl1BvKnyLmp2M0MDooJI35wM0YK00hmwZprBuPlqPMZSFQmQrPnUeYWqH6JUKRwmqZguoX30D74Frs1OMVrDhjATKCqcSQ99wFPpfM_tGYXMb3gu_BYwzm_VXVix7XFBtvIH6EyWcMN7sI8Gbnk8oTl2MWNKpg_DollxvA72g6CNPZ5kg9gy0rQWwtn0w5JN3g9gqMZjEoSNWdQAIxey82rf2OqCb9mtauehTncreZoUYQPcX5SHz3jFrGa2-wO3j1SW7sw_W61T7qA4fHOsKRNqaDBfXYSCqyKpLxYqbfZC2Rsw0BXgUscwh2igja3uy-1IirLJmdMo0ilHGBJbzhHp9EUhK5xJbMKc5LHzkgZ1KTtiHDVDdFBo7pMPK5fLjZvRlkXvHTSP7v8c27YNn998pu6I_9qfF3XhuKWv0WoOYdjDc24jVZwGMhg2D4JNvK3j2mQ-xl7xh2-dEiJcVFLkDDGB6D3yXWDZuYDHsUU9PRviqqenjJP85U2DcOEvBylc_rShWbEP=w219-h78-no?authuser=0',
        width: '11rem',
        height: '4rem',
        margin: '1rem 1rem 0rem 0rem',
        showFavicon: true,
        showCounter: false
      },
      isAuth: false,
      show: false
    }
  },
  methods: {
    switchShowing() {
      this.isAuth == true ? this.show = true : this.show = false;
    },
    emitedIsAuth(event) {
      this.isAuth = event;
    },
    changeIsAuth(event) {
      this.isAuth = event;
    }
  },
  beforeMount() {
    this.switchShowing();
  }
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: Roboto sans-serif;
}

.main {
  height: 100vh;
  width: 100vw;
  background: #596c94;
  display: flex;
}

.wrapper-row {
  display: flex;
  flex-direction: row;
}

.wrapper-for-enter {
  display: flex;
  justify-content: center;
  margin-top: 25rem;
}

.someclass {
  width: calc(100vw/10*7.2);
  display: flex;
  flex-direction: column;
}

@media (max-width: 1600px) {
  * {
    font-size: 95%;
  }
}

@media (max-width: 1400px) {
  * {
    font-size: 90%;
  }
}

@media (max-width: 1200px) {
  * {
    font-size: 85%;
  }
}
</style>
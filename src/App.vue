<template>
  <div>
    <div class="wrapper-for-enter" v-if="isAuth == false">
      <enter @click="emitedIsAuth" />
    </div>
    <div class="main" v-else="">
      <sidebar style="width: calc(100vw/10*2.8);
       padding: 2.3rem;
       border-top-right-radius: 1.5rem;
       border-bottom-right-radius: 1.5rem;" @emited-from-sidebar="changeIsAuth" />
      <div class="someclass">

      </div>
    </div>
  </div>

</template>

<script>
import UserView from '@/components/UserView.vue'
import Sidebar from '@/components/Sidebar.vue'
import Enter from './components/Enter.vue'

export default {
  components: {
    UserView,
    Sidebar,
    Enter
  },
  data() {
    return {
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
  },
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main {
  height: 100vh;
  width: 100vw;
  background: #596c94;
  display: flex;
}

.wrapper-for-enter {
  display: flex;
  justify-content: center;
  margin-top: 17rem;
}

.someclass {
  width: calc(100vw/10*7.2);
}
</style>
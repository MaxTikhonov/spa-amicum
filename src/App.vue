<template>
  <div class="main" v-show="show">
    <sidebar
      style="width: calc(100vw/10*2.8); padding: 2.3rem;border-top-right-radius: 1.5rem;border-bottom-right-radius: 1.5rem;" />
    <div class="someclass">

    </div>
  </div>
</template>

<script>
import UserView from '@/components/UserView.vue'
import Sidebar from '@/components/Sidebar.vue'

export default {
  components: {
    UserView,
    Sidebar
  },
  data() {
    return {
      show: true
    }
  }
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

.someclass {
  width: calc(100vw/10*7.2);
}
</style>
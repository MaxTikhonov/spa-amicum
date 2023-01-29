<template>
  <slot></slot>
  <div style="margin-left: .22rem;"><image-icon @emited-auth="emitedFromImageIcon"
      :infoForImage="infoForImage"></image-icon></div>
</template>

<script>

export default {
  name: 'enter-and-out',
  emits: ["updatedcount"],
  data() {
    return {
      isAuthOut: true,
      infoForImage: {
        showFavicon: true,
        srcOfImage: 'https://img.icons8.com/laces/64/FFFFFF/import.png',
        width: '3.5rem',
        height: '3.5rem',
        fromAutoFill: false,
      }
    }
  },
  watch: {
    isAuthOut(newValue, oldValue) {
      if (newValue == false) {
        this.$emit('emited-from-enterandout', newValue);
      }
      else {
      }
    }
  },
  methods: {
    emitedFromImageIcon(event) {
      console.log(event)
      this.isAuthOut = event;
    }
  }
}
</script>

<style scoped>

</style>
<template>
  <div
    class="w-16 h-16 border-black border flex justify-center items-center overflow-hidden relative"
    @mouseenter="isHover = !isHover"
    @mouseleave="isHover = !isHover"
  >
    <font-awesome-icon :icon="['fas', 'chevron-up']" class="z-10" />
    <div
      class="w-full bg-black h-16 absolute top-60 transition-all duration-500"
      :class="isHover ? 'top--70' : 'top-60'"
    ></div>
    <span
      class="w-full bg-black absolute bottom-0 transition-all duration-100 delay-200"
      :class="isHover ? 'h-3px' : 'h-0'"
    ></span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHover: false,
    }
  },
}
</script>

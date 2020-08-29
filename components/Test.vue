<template>
  <div
    class="w-full h-20 flex items-center justify-center bg-black cursor-pointer move-hover lg:inline-block"
  >
    <div class="w-6 h-6 relative overflow-hidden">
      <span class="absolute w-full h-1 bg-white top-0"></span>
      <span class="absolute w-full h-1 bg-black top-0 left-30 move"></span>
      <span class="absolute w-full h-1 bg-white bottom-0"></span>
      <span class="absolute w-full h-1 bg-black bottom-0 left--30 move2"></span>
    </div>
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
<style scoped>
.move-hover:hover .move {
  animation-name: example;
  animation-duration: 0.5s;
}
.move-hover:hover .move2 {
  animation-name: example2;
  animation-duration: 0.5s;
}
@keyframes example {
  0% {
    left: 30px;
  }

  100% {
    left: -30px;
  }
}
@keyframes example2 {
  0% {
    left: -30px;
  }

  100% {
    left: 30px;
  }
}
</style>

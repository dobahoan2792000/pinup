<template>
  <div :class="isInShop ? 'fixed bottom-60-right-60px' : 'hidden'">
    <div
      class="w-10 h-10 border-black border overflow-hidden relative move-hover"
      @mouseenter="isHover = !isHover"
      @mouseleave="isHover = !isHover"
    >
      <a href="#" class="w-full h-full flex justify-center items-center">
        <font-awesome-icon
          :icon="['fas', 'chevron-up']"
          class="z-10 text-sm"
          :class="[isHover ? 'move' : 'move2']"
        />
        <div
          class="w-full h-16 absolute top-35 transition-all duration-500"
          :class="[isHover ? 'top--70' : 'top-35']"
        ></div>
        <span
          class="w-full absolute bottom-0 transition-all duration-100 delay-200"
          :class="[isHover ? 'h-3px' : 'h-0']"
        ></span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Ontop',
  props: {
    isInShop: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isHover: false,
    }
  },
}
</script>
<style scoped>
.move-hover:hover .move {
  animation-name: shop;
  animation-duration: 1s;
}
@keyframes shop {
  0% {
    color: black;
  }
  25% {
    color: white;
  }
  50% {
    color: black;
  }
  100% {
    color: black;
  }
}
.move2 {
  animation-name: shop2;
  animation-duration: 1s;
}
@keyframes shop2 {
  0% {
    color: black;
  }
  25% {
    color: white;
  }
  50% {
    color: black;
  }
  100% {
    color: black;
  }
}
.move-hover:hover .move-footer {
  animation-name: footer;
  animation-duration: 1s;
}
@keyframes footer {
  0% {
    color: white;
  }
  25% {
    color: black;
  }
  50% {
    color: white;
  }
  100% {
    color: white;
  }
}
.move-footer2 {
  animation-name: footer2;
  animation-duration: 1s;
}
@keyframes footer2 {
  0% {
    color: white;
  }
  25% {
    color: white;
  }
  50% {
    color: black;
  }
  75% {
    color: black;
  }
  100% {
    color: black;
  }
}
.bottom-60-right-60px {
  bottom: 60px;
  right: 60px;
}
</style>

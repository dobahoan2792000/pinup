<template>
  <div
    class="w-screen h-screen bg-crystal fixed top-0"
    :class="selectedNumber >= 0 ? 'block' : 'hidden'"
  >
    <div
      v-for="(img, index) in arrImgs"
      :key="img.index"
      class="absolute center z-10 transition-all duration-500"
      :class="[
        index == selectedNumber ? 'opacity-100' : 'opacity-0',
        isExpand ? 'xl:w-1/2 md:w-9/12 w-11/12' : 'xl:w-4/12 md:w-6/12 w-10/12',
      ]"
      @mouseenter="isHover = !isHover"
      @mouseleave="isHover = !isHover"
    >
      <div class="absolute top-negative-20" @click="expandDisplay">
        <font-awesome-icon
          :icon="['fas', 'expand']"
          class="text-white cursor-pointer"
        />
      </div>
      <img :src="img.url" alt="" class="w-full" />
      <div class="absolute valign right-0 mr-3" @click="getNumberUp">
        <svg
          class="text-gray-800 text-2xl cursor-pointer rotate-180 hover:text-gray-700"
          :class="isHover ? 'block' : 'hidden'"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          focusable="false"
          width="1em"
          height="1em"
          style="
            -ms-transform: rotate(180deg);
            -webkit-transform: rotate(180deg);
            transform: rotate(180deg);
          "
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 20 20"
        >
          <path
            d="M13.891 17.418a.697.697 0 0 1 0 .979a.68.68 0 0 1-.969 0l-7.83-7.908a.697.697 0 0 1 0-.979l7.83-7.908a.68.68 0 0 1 .969 0a.697.697 0 0 1 0 .979L6.75 10l7.141 7.418z"
            class="fill-current"
          />
        </svg>
      </div>
      <div class="absolute valign left-0 ml-3" @click="getNumberDown">
        <svg
          class="text-gray-800 text-2xl cursor-pointer hover:text-gray-700"
          :class="isHover ? 'block' : 'hidden'"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          focusable="false"
          width="1em"
          height="1em"
          style="
            -ms-transform: rotate(360deg);
            -webkit-transform: rotate(360deg);
            transform: rotate(360deg);
          "
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 20 20"
        >
          <path
            d="M13.891 17.418a.697.697 0 0 1 0 .979a.68.68 0 0 1-.969 0l-7.83-7.908a.697.697 0 0 1 0-.979l7.83-7.908a.68.68 0 0 1 .969 0a.697.697 0 0 1 0 .979L6.75 10l7.141 7.418z"
            class="fill-current"
          />
        </svg>
      </div>
      <div
        class="h-12 w-full bg-white flex items-center relative"
        :class="isExpand ? 'hidden' : 'block'"
      >
        <div class="flex ml-6">
          <svg
            class="text-gray-600 text-xl hover:text-gray-800 cursor-pointer rotate-180"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            aria-hidden="true"
            focusable="false"
            width="1em"
            height="1em"
            style="
              -ms-transform: rotate(180deg);
              -webkit-transform: rotate(180deg);
              transform: rotate(180deg);
            "
            preserveAspectRatio="xMidYMid meet"
            viewBox="0 0 20 20"
            @click="getNumberUp"
          >
            <path
              d="M9.163 4.516c.418.408 4.502 4.695 4.502 4.695a1.095 1.095 0 0 1 0 1.576s-4.084 4.289-4.502 4.695c-.418.408-1.17.436-1.615 0c-.446-.434-.481-1.041 0-1.574L11.295 10L7.548 6.092c-.481-.533-.446-1.141 0-1.576c.445-.436 1.197-.409 1.615 0z"
              class="fill-current"
            />
          </svg>
          <svg
            class="text-gray-600 text-xl hover:text-gray-800 cursor-pointer"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            aria-hidden="true"
            focusable="false"
            width="1em"
            height="1em"
            style="
              -ms-transform: rotate(360deg);
              -webkit-transform: rotate(360deg);
              transform: rotate(360deg);
            "
            preserveAspectRatio="xMidYMid meet"
            viewBox="0 0 20 20"
            @click="getNumberDown"
          >
            <path
              d="M9.163 4.516c.418.408 4.502 4.695 4.502 4.695a1.095 1.095 0 0 1 0 1.576s-4.084 4.289-4.502 4.695c-.418.408-1.17.436-1.615 0c-.446-.434-.481-1.041 0-1.574L11.295 10L7.548 6.092c-.481-.533-.446-1.141 0-1.576c.445-.436 1.197-.409 1.615 0z"
              class="fill-current"
            />
          </svg>
        </div>
        <p class="absolute align font-mon text-sm text-gray-600 font-bold">
          {{ index + 1 }} / 4
        </p>
      </div>
    </div>
    <div class="absolute w-full h-full" @click="getHidden"></div>
  </div>
</template>

<script>
export default {
  name: 'Slide',
  props: {
    arrImgs: {
      type: Array,
      required: true,
    },
    isExpand: {
      type: Boolean,
      required: true,
    },
    selectedNumber: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      number: 0,
      isHover: false,
      images: [
        {
          url: '/img/item/item1/1.jpg',
        },
        {
          url: '/img/item/item1/2.jpg',
        },
        {
          url: '/img/item/item1/3.jpg',
        },
        {
          url: '/img/item/item1/4.jpg',
        },
      ],
    }
  },
  methods: {
    // changeExpand(){
    //    if (this.isExpand === true) this.isExpand = false
    // }
    getNumberUp() {
      this.$emit('cong')
    },
    getNumberDown(index) {
      this.$emit('tru')
    },
    slideDisplay() {
      this.$emit('changeDisplaySlide')
    },
    expandDisplay() {
      this.$emit('expand')
    },
    getHidden() {
      this.$emit('hiddenDisplay')
    }
  },
}
</script>
<style scoped>
.width-35 {
  width: 35%;
}
.width-40 {
  width: 40%;
}
.width-50 {
  width: 50%;
}
.top-negative-20 {
  top: -20px;
  right: -20px;
}
</style>

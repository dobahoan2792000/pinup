<template>
  <div
    class="fixed top-0 w-screen h-screen bg-crystal flex transition-all duration-500 z-10"
    :class="isClose ? 'visible' : 'invisible delay-400'"
  >
    <div class="w-3/5 h-full" @click="getClose"></div>
    <div
      :class="isClose ? 'right0' : ''"
      class="w-2/5 bg-black h-full box-border px-8 py-10 lg:px-16 lg:py-20 absolute transition-all duration-1000 right-40"
    >
      <div class="absolute top-0 right-0">
        <font-awesome-icon
          :icon="['fas', 'times']"
          class="text-white cursor-pointer mt-8 mr-8 text-lg float-right"
          @click="getClose"
        />
      </div>
      <div class="w-full">
        <div class="w-full mb-16">
          <a href="#">
            <img src="/img/logo-popup.png" alt="logo-popup" />
          </a>
        </div>
        <div @mouseover="isHover = !isHover" @mouseout="isHover = !isHover">
          <div class="overflow-hidden">
            <a href="#" class="w-full flex justify-center">
              <img
                src="/img/logo-popup2.png"
                alt=""
                class="inline-block transition-all duration-500"
                :class="isHover ? 'scale1-05' : ''"
              />
            </a>
          </div>
        </div>
        <div class="w-full flex flex-wrap justify-center px-10 pt-8">
          <div>
            <span class="font-mon font-sub-menu text-white font-bold uppercase"
              >May 8,2020</span
            >
            <span class="font-mon font-sub-menu text-white font-bold uppercase"
              >Stylish</span
            >
          </div>
          <a
            href="#"
            class="block w-full text-center"
            @mouseover="isHover = !isHover"
            @mouseout="isHover = !isHover"
          >
            <span
              class="font-vida text-2xl text-white transition-all duration-200"
              :class="isHover ? 'underline' : ''"
              >Fashion is Not Necessarily About Labels or Brands</span
            >
          </a>
          <div>
            <span class="font-mon font-sub-menu text-white font-bold uppercase"
              >By</span
            >
            <a
              href="#"
              class="font-mon font-sub-menu text-white font-bold uppercase"
              >Pinupadmin</a
            >
          </div>
        </div>
      </div>
      <div class="absolute bottom-0 align">
        <div class="flex justify-center mb-8 mt-3 mx-auto">
          <a
            href="#"
            class="p-3 border-white-1px flex items-center group hover:bg-white"
          >
            <font-awesome-icon
              :icon="['fab', 'facebook-f']"
              class="text-white text-xs group-hover:text-black"
            />
          </a>

          <a
            href="#"
            class="p-3 border-white-1px flex items-center group hover:bg-white"
          >
            <font-awesome-icon
              :icon="['fab', 'twitter']"
              class="text-white text-xs group-hover:text-black"
            />
          </a>
          <a
            href="#"
            class="p-3 border-white-1px flex items-center group hover:bg-white"
          >
            <font-awesome-icon
              :icon="['fab', 'instagram']"
              class="text-white text-xs group-hover:text-black"
            />
          </a>
          <a
            href="#"
            class="p-3 border-white-1px flex items-center group hover:bg-white"
            @click="isClose"
          >
            <font-awesome-icon
              :icon="['fab', 'pinterest-p']"
              class="text-white text-xs group-hover:text-black"
            />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Introduce',
  props: {
    isClose: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isHover: false,
    }
  },
  methods: {
    getClose() {
      console.log('1')
      this.$emit('changeDisplay')
    },
  },
}
</script>

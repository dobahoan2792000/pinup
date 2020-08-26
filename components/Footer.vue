<template>
  <div class="mt-20">
    <div
      class="w-full bg-black border-b border-gray-600 flex justify-center flex-wrap px-20 py-20"
    >
      <div class="w-5/6 flex justify-center">
        <img src="/img/Footer/footer1.png" class="inline-block" alt="" />
      </div>
      <div class="w-full h-16"></div>
      <div class="w-full flex justify-center">
        <div class="w-2/5 flex justify-center flex-wrap relative">
          <form
            action=""
            class="inline-flex items-center py-3 w-full transition-all duration-300 relative"
          >
            <input
              type="email"
              placeholder="email*"
              class="bg-black text-white outline-none border=none w-full"
              @focus="isFocus = !isFocus"
              @blur="isFocus = !isFocus"
            />
            <input type="submit" value="" class="bg-black text-white" />
          </form>
          <span
            class="w-full bg-white absolute bottom-0 transition-all duration-100"
            :class="isFocus ? 'h-3px' : 'h-1px'"
          ></span>
        </div>
      </div>
    </div>
    <div
      class="bg-black flex lg:items-center lg:justify-between flex-wrap lg:px-8 lg:py-4"
    >
      <div class="w-full lg:w-1/3 flex mt-10 mb-16 lg:my-0">
        <img
          src="/img/Footer/footer2.png"
          alt="ft"
          class="inline-block mx-auto lg:mx-0"
        />
      </div>
      <div class="w-full lg:w-1/3 flex lg:justify-center justify-center">
        <div>
          <a href="#" class="mx-3">
            <font-awesome-icon
              :icon="['fab', 'facebook-f']"
              class="text-white hover:text-gray-400 transition-all duration-300"
            />
          </a>

          <a href="#" class="mx-3">
            <font-awesome-icon
              :icon="['fab', 'instagram']"
              class="text-white hover:text-gray-400 transition-all duration-300"
            />
          </a>
          <a href="#" class="mx-3">
            <font-awesome-icon
              :icon="['fab', 'pinterest-p']"
              class="text-white hover:text-gray-400 transition-all duration-300"
            />
          </a>
          <a href="#" class="mx-3">
            <font-awesome-icon
              :icon="['fab', 'youtube']"
              class="text-white hover:text-gray-400 transition-all duration-300"
            />
          </a>
        </div>
      </div>
      <div
        class="w-full lg:w-1/3 flex lg:justify-end justify-center my-10 lg:my-0"
      >
        <span class="text-white font-mon text-sm"
          >© Copyright Pinup Vintage House 2018</span
        >
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isFocus: false,
    }
  },
  methods: {},
}
</script>

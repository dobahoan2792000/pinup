<template>
  <div
    :class="isCloseSearch ? 'opacity-100 visible' : 'opacity-0 invisible'"
    class="z-10"
  >
    <div class="fixed h-screen w-screen top-0 left-0 bg-black">
      <div class="absolute right-0">
        <font-awesome-icon
          :icon="['fas', 'times']"
          class="text-white cursor-pointer mr-12 mt-8 text-2xl float-right"
          @click="getClose"
        />
      </div>
      <div class="flex w-screen h-screen justify-center items-center">
        <form
          action=""
          class="w-3/5 flex items-center pb-2 relative overflow-hidden"
        >
          <font-awesome-icon
            :icon="['fas', 'search']"
            class="text-white cursor-pointer text-lg absolute top-60 transition-all duration-1000"
            :class="isCloseSearch ? 'valign-searchbox' : ''"
          />
          <input
            type="text"
            placeholder="TYPE YOUR SEARCH"
            class="bg-black font-mon tracking-widest text-xs border-none outline-none text-white w-full py-4 pl-3 ml-4"
          />
          <span
            class="absolute h-1px bg-white bottom-0 w-0 transition-all duration-1000"
            :class="isCloseSearch ? 'w-full' : ''"
          ></span>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    isCloseSearch: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {}
  },
  methods: {
    getClose() {
      this.$emit('changeDisPlaySearch')
    },
  },
}
</script>

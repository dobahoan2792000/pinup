<template>
  <div class="hidden lg:flex lg:justify-center lg:py-2 lg:w-full">
    <div class="flex justify-between w-4/5">
      <div>
        <a
          href="#"
          class="mx-1 hover:text-gray-800 transition-all duration-300"
        >
          <font-awesome-icon :icon="['fab', 'facebook-f']" />
        </a>

        <a
          href="#"
          class="mx-1 hover:text-gray-800 transition-all duration-300"
        >
          <font-awesome-icon :icon="['fab', 'instagram']" />
        </a>
        <a
          href="#"
          class="mx-1 hover:text-gray-800 transition-all duration-300"
        >
          <font-awesome-icon :icon="['fab', 'pinterest-p']" />
        </a>
        <a
          href="#"
          class="mx-1 hover:text-gray-800 transition-all duration-300"
        >
          <font-awesome-icon :icon="['fab', 'youtube']" />
        </a>
      </div>
      <div>
        <a href="#" class="flex items-center">
          <font-awesome-icon :icon="['fas', 'envelope']" />
          <span class="uppercase font-mon font-menu tracking-widest px-2"
            >Subscribe</span
          >
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  methods: {},
}
</script>

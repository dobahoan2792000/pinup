<template>
  <div>
    <form class="flex justify-center flex-wrap">
      <table class="w-4/5 md:w-5/6">
        <tr class="border-b border-gray-400">
          <th class="sm:w-8 md:w-16 lg:w-32 py-6 text-left"></th>
          <th class="w-0 md:w-20"></th>
          <th class="text-left font-vida text-sm">Products</th>
          <th class="text-left font-vida text-sm">Price</th>
          <th class="text-left font-vida text-sm">Quantity</th>
          <th class="text-left font-vida text-sm">Total</th>
        </tr>
        <tr
          v-for="product in products"
          :key="product.url"
          class="border-b border-gray-400"
        >
          <td class="py-12">
            <font-awesome-icon
              :icon="['fas', 'times']"
              class="text-gray-500 text-xs cursor-pointer"
            />
          </td>
          <td class="pr-2 w-0 md:w-20">
            <img :src="product.url" alt="" class="w-0 md:w-full" />
          </td>
          <td>
            <span class="font-mon text-xs text-gray-800">{{
              product.name
            }}</span>
          </td>
          <td>
            <span class="font-mon text-xs text-gray-800">{{
              product.price
            }}</span>
          </td>
          <td>
            <div class="count-box-sm border border-black relative">
              <div
                class="absolute h-full width-38 border-r border-black box-border flex items-center justify-center"
              >
                <span class="font-mon text-xs">{{ product.quantity }}</span>
              </div>
              <div
                class="absolute height-50 width-19 right-0 top-0 flex items-center justify-center"
              >
                <font-awesome-icon
                  :icon="['fas', 'angle-up']"
                  class="text-xs cursor-pointer margin-left-1"
                />
              </div>
              <div
                class="absolute height-50 width-19 right-0 bottom-0 flex items-center justify-center"
              >
                <font-awesome-icon
                  :icon="['fas', 'angle-down']"
                  class="text-xs cursor-pointer margin-left-1"
                />
              </div>
            </div>
          </td>
          <td>
            <span class="font-mon text-xs text-gray-800">{{
              product.price * product.quantity
            }}</span>
          </td>
        </tr>
      </table>
      <div class="w-4/5 mt-6 md:flex md:flex-no-wrap md:justify-between">
        <div class="w-full md:w-1/2 flex flex-wrap md:flex-no-wrap">
          <input
            type="text"
            placeholder="Coupon code"
            class="outline-none py-2 border-b border-black font-mon text-xs w-full md:w-1/3"
          />
          <div
            class="w-2/3 px-6 md:px-3 lg:w-1/3 py-3 md:py-3 border-black border overflow-hidden relative move-hover mt-8 md:mt-0 md:ml-8 cursor-pointer"
            @mouseenter="isHoverApply = !isHoverApply"
            @mouseleave="isHoverApply = !isHoverApply"
          >
            <a href="#" class="w-full h-full flex justify-center items-center">
              <span
                class="font-mon font-menu uppercase z-10"
                :class="[isHoverApply ? 'move' : 'move2']"
                >Apply coupon</span
              >
              <div
                class="w-full h-16 absolute transition-all duration-500 bg-black"
                :class="[isHoverApply ? 'top--70' : 'top-40']"
              ></div>
              <span
                class="w-full absolute bottom-0 transition-all duration-100 delay-200 bg-black"
                :class="[isHoverApply ? 'h-3px' : 'h-0']"
              ></span>
            </a>
          </div>
        </div>
        <div
          class="w-2/3 md:w-1/3 lg:w-2/12 px-6 md:px-3 py-3 border-black border overflow-hidden relative move-hover cursor-pointer mt-3 sm:mt-8 md:mt-0"
          @mouseenter="isHoverUpdate = !isHoverUpdate"
          @mouseleave="isHoverUpdate = !isHoverUpdate"
        >
          <a href="#" class="w-full h-full flex justify-center items-center">
            <span
              class="font-mon font-menu uppercase z-10"
              :class="[isHoverUpdate ? 'move' : 'move2']"
              >Update Cart</span
            >
            <div
              class="w-full h-16 absolute transition-all duration-500 bg-black"
              :class="[isHoverUpdate ? 'top--70' : 'top-40']"
            ></div>
            <span
              class="w-full absolute bottom-0 transition-all duration-100 delay-200 bg-black"
              :class="[isHoverUpdate ? 'h-3px' : 'h-0']"
            ></span>
          </a>
        </div>
      </div>
    </form>
    <div class="w-full flex justify-center mt-10 flex-wrap">
      <div class="w-4/5">
        <h2 class="font-vida text-xl mb-8">Cart totaols</h2>
        <table class="w-full">
          <tr class="border-b border-gray-300">
            <th class="text-left font-vida text-sm w-1/5 py-3 text-gray-700">Subtotal</th>
            <td><span class="font-vida text-xs text-gray-500 ml-3">20000</span></td>
          </tr>
          <tr class="border-b border-gray-300">
            <th class="text-left font-vida text-sm py-3 text-gray-700">Total</th>
            <td class="font-vida text-xs"><span class="ml-3">20000</span></td>
          </tr>
        </table>
      </div>
      <div class="w-4/5 mt-6">
        <div
          class="w-3/4 sm:w-1/2 md:1/4 px-6 py-3 border-black border overflow-hidden relative move-hover cursor-pointer mt-8 md:mt-0"
          @mouseenter="isHoverCheckout = !isHoverCheckout"
          @mouseleave="isHoverCheckout = !isHoverCheckout"
        >
          <a href="#" class="w-full h-full flex justify-center items-center">
            <span
              class="font-mon font-menu uppercase z-10"
              :class="[isHoverCheckout ? 'move' : 'move2']"
              >Update Cart</span
            >
            <div
              class="w-full h-16 absolute transition-all duration-500 bg-black"
              :class="[isHoverCheckout ? 'top--70' : 'top-40']"
            ></div>
            <span
              class="w-full absolute bottom-0 transition-all duration-100 delay-200 bg-black"
              :class="[isHoverCheckout ? 'h-3px' : 'h-0']"
            ></span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHover: false,
      isHoverApply: false,
      isHoverUpdate: false,
      isHoverCheckout: false,
      sum: 0,
      products: [
        {
          url: '/img/Item/item1/1.jpg',
          name: 'Peach Coat',
          price: 20000,
          quantity: 1,
        },
        {
          url: '/img/Item/item1/2.jpg',
          name: 'Peach Coat',
          price: 20000,
          quantity: 1,
        },
      ],
    }
  },
  methods: {},
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
</style>

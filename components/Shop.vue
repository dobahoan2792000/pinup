<template>
  <div class="w-full flex justify-center pt-20 flex-wrap">
    <div class="w-4/6 md:w-5/6 md:px-4">
      <div class="md:flex md:items-center md:justify-between">
        <p class="mb-10 font-mon text-sm text-gray-700 md:mb-0">
          Showing 1-12 of 18 results
        </p>
        <div
          class="relative inline-block w-3/5 md:w-3/12 border border-gray-400"
        >
          <select
            name="sort"
            class="form-select px-3 py-3 appearance-none font-mon text-sm focus:outline-none text-gray-800 w-full"
          >
            <option value="">Default sorting</option>
            <option value="">Sort by popularity</option>
            <option value="">Sort by average rating</option>
            <option value="">Sort by latest</option>
            <option value="">Sort by price: low to high</option>
            <option value="">Sort by price: high to low</option>
          </select>
          <div
            class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
          >
            <svg
              class="rotate-90"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              aria-hidden="true"
              focusable="false"
              width="1em"
              height="1em"
              preserveAspectRatio="xMidYMid meet"
              viewBox="0 0 20 20"
            >
              <path
                d="M9.163 4.516c.418.408 4.502 4.695 4.502 4.695a1.095 1.095 0 0 1 0 1.576s-4.084 4.289-4.502 4.695c-.418.408-1.17.436-1.615 0c-.446-.434-.481-1.041 0-1.574L11.295 10L7.548 6.092c-.481-.533-.446-1.141 0-1.576c.445-.436 1.197-.409 1.615 0z"
                class="fill-current"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
    <div id="products" class="flex mt-10 w-4/6 md:w-5/6 flex-wrap">
      <div
        v-for="product in products"
        :key="product.url"
        class="w-full md:w-1/2 md:px-4 lg:w-1/3"
      >
        <div class="group">
          <div class="w-full relative">
            <a :href="product.link">
              <img :src="product.url" alt="product" class="w-full" />
              <div
                class="absolute bottom-0 w-full h-0 opacity-0 bg-black transition-all duration-150 flex items-center justify-center group-hover:h-12 group-hover:opacity-100"
              >
                <span
                  class="font-mon tracking-widest text-gray-300 uppercase text-xs py-2"
                  >Add to cart</span
                >
              </div></a
            >
          </div>

          <div class="mt-5 mb-10">
            <div class="flex justify-between pb-3">
              <a :href="product.link"
                ><span class="font-vida text-lg">{{ product.name }}</span></a
              >
              <span class="font-vida text-sm"> {{ product.price }}₫ </span>
            </div>
            <a :href="product.link">
              <p class="font-mon font-sub-menu tracking-widest uppercase">
                {{ product.kind }}
              </p>
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="w-4/6 md:w-5/6 flex justify-end md:px-4">
      <a
        href="#"
        class="border border-black h-8 w-8 flex justify-center items-center mr-2"
      >
        <span class="text-black font-mon text-sm">1</span>
      </a>
      <a
        href="#"
        class="border border-black h-8 w-8 flex justify-center items-center mr-2 bg-black group hover:bg-white"
      >
        <span class="text-white font-mon text-sm group-hover:text-black"
          >2</span
        >
      </a>
      <a
        href="#"
        class="border border-black h-8 w-8 flex justify-center items-center bg-black group hover:bg-white"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          focusable="false"
          width="1em"
          height="1em"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 20 20"
        >
          <path
            d="M9.163 4.516c.418.408 4.502 4.695 4.502 4.695a1.095 1.095 0 0 1 0 1.576s-4.084 4.289-4.502 4.695c-.418.408-1.17.436-1.615 0c-.446-.434-.481-1.041 0-1.574L11.295 10L7.548 6.092c-.481-.533-.446-1.141 0-1.576c.445-.436 1.197-.409 1.615 0z"
            class="fill-current text-white group-hover:text-black"
          />
        </svg>
      </a>
    </div>
    <Ontop :isInShop="isInShop" />
  </div>
</template>
<script>
import Ontop from '~/components/Ontop.vue'
export default {
  components: { Ontop },
  data() {
    return {
      isInShop: false,
      products: [
        {
          url: '/img/Products/1.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '75,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/2.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '75,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/3.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '20,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/4.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '35,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/5.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '15,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/6.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '80,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/7.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '35,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/8.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '90,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/9.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '80,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/10.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '65,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/11.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '50,0',
          kind: 'Business',
        },
        {
          url: '/img/Products/12.jpg',
          link: '#',
          name: 'Turquoise Bag',
          price: '90,0',
          kind: 'Business',
        },
      ],
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      const el = document.querySelector('#products')
      const elDistanceToTop = el.getBoundingClientRect().top
      if (elDistanceToTop < 0) {
        this.isInShop = true
        console.log('Đây la < 0 ', elDistanceToTop)
      } else {
        this.isInShop = false
        console.log('Đây la > 0 ', elDistanceToTop)
      }
    })
  },
  methods: {},
}
</script>

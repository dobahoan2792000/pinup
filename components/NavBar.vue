<template>
  <header
    class="w-full lg:flex lg:flex-wrap lg:box-border"
    :class="isShowNavBar ? 'lg:fixed lg:top-0 lg:z-10' : 'lg:relative'"
  >
    <div
      class="flex py-6 px-10 justify-between border-b leading-3 lg:p-0 lg:border-0"
    >
      <div>
        <button
          type="button"
          class="block text-black hover:text-gray-500 focus:outline-none lg:hidden"
          @click="isOpen = !isOpen"
        >
          <svg class="h-4 w-4 fill-current" viewBox="0 0 24 24">
            <path
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            />
          </svg>
        </button>
      </div>
      <picture class="max-w-md h-5 mx-auto lg:hidden">
        <img src="/img/logo-standard-dark.png" alt="Flowers" class="h-4" />
      </picture>
    </div>
    <nav
      class="absolute lg:static left-0 bg-white w-full z-10 lg:z-0 lg:flex lg:align-middle lg:bg-black lg:text-center lg:items-center lg:h-20 transition-all duration-300 overflow-scroll lg:overflow-visible"
      :class="isOpen ? 'h-64' : 'h-0'"
    >
      <!-- <svg
        class="eltdf-burger lg:ml-20 xl:ml-32 hidden lg:block cursor-pointer"
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        x="0px"
        y="0px"
        width="14.998px"
        height="14.998px"
        viewBox="0 0 14.998 14.998"
        enable-background="new 0 0 14.998 14.998"
        xml:space="preserve"
        @click="isCloseEvent"
      >
        <rect
          class="eltdf-burger-bar-1 lg:text-white lg:fill-current"
          width="14.998"
          height="2.993"
        ></rect>
        <rect
          class="eltdf-burger-bar-2 lg:text-white lg:fill-current"
          y="12.005"
          width="14.998"
          height="2.993"
        ></rect>
      </svg> -->

      <div
        class="w-5 h-4 relative overflow-hidden hidden lg:inline-block lg:ml-20 xl:ml-32 cursor-pointer move-hover"
        @click="isCloseEvent"
      >
        <span class="absolute w-full h-3px bg-white top-0 left-0"></span>
        <span class="absolute w-full h-3px bg-black top-0 left-30 move"></span>
        <span class="absolute w-full h-3px bg-white bottom-0 left-0"></span>
        <span
          class="absolute w-full h-3px bg-black bottom-0 left--30 move2"
        ></span>
      </div>

      <ul
        class="mx-10 lg:flex lg:h-full lg:w-4/5 transition-opacity duration-500 lg:visible lg:opacity-100"
        :class="isOpen ? 'visible opacity-1' : 'invisible opacity-0'"
      >
        <li
          v-for="item in menu"
          :key="item.title"
          class="line-hover lg:relative"
          @mouseenter="item.isOpen = !item.isOpen"
          @mouseleave="item.isOpen = !item.isOpen"
        >
          <a
            :href="item.link"
            class="font-menu lg:font-menu-lg py-3 flex justify-between border-b lg:border-0 lg:items-center lg:px-3 xl:px-6 xl:font-menu-xl lg:h-full lg:leading-6 lg:font-mon"
            @click="item.isOpenMobile = !item.isOpenMobile"
            ><span
              class="lg:relative lg:tracking-widest lg:line-w uppercase lg:text-white lg:font-medium"
              >{{ item.title }}</span
            >
            <svg
              class="font-menu inline-block my-auto lg:hidden transition-all duration-300"
              :class="item.isOpenMobile ? 'rotate-90' : 'rotate-0'"
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
                fill="#626262"
              />
            </svg>
          </a>
          <transition name="slide">
            <div
              v-if="item.isOpen"
              class="lg:absolute lg:left-0 lg:bg-black lg:transition-height lg:transition-opacity lg:duration-100 lg:flex lg:items-center"
              :class="[item.isOpenMobile ? 'block' : 'hidden']"
            >
              <ul
                v-if="item.children && item.children.length"
                class="lg:py-8"
                :class="item.isVintage ? 'lg:w-64' : ' lg:w-56'"
              >
                <li
                  v-for="subitem in item.children"
                  :key="subitem.title"
                  class="dothover relative"
                  @mouseenter="subitem.isOpenMobile = !subitem.isOpenMobile"
                  @mouseleave="subitem.isOpenMobile = !subitem.isOpenMobile"
                >
                  <a
                    :href="subitem.link"
                    class="font-sub-menu font-mon lg:font-bold flex justify-between ml-3 lg:py-1 py-3 border-b lg:border-0 lg:text-white lg:ml-0 lg:text-left lg:px-6"
                    @click="subitem.isOpen = !subitem.isOpen"
                    ><span
                      class="lg:relative lg:w-full lg:dot lg:tracking-widest"
                    >
                      <span class="uppercase">{{ subitem.title }}</span>
                    </span>
                    <svg
                      :class="[
                        subitem.children ? 'block' : 'hidden',
                        subitem.isOpen ? 'rotate-90' : 'rotate-0',
                      ]"
                      class="font-menu inline-block my-auto lg:text-white"
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
                        d="M9.163 4.516c.418.408 4.502 4.695 4.502 4.695a1.095 1.095 0 0 1 0 1.576s-4.084 4.289-4.502 4.695c-.418.408-1.17.436-1.615 0c-.446-.434-.481-1.041 0-1.574L11.295 10L7.548 6.092c-.481-.533-.446-1.141 0-1.576c.445-.436 1.197-.409 1.615 0z"
                        class="fill-current"
                      />
                    </svg>
                  </a>
                  <ul
                    v-if="subitem.children"
                    :class="[
                      subitem.isOpen ? 'block' : 'hidden',
                      subitem.isOpenMobile ? 'lg:block' : 'lg:hidden',
                    ]"
                    class="lg:absolute lg:bg-black lg:left-224 lg:w-full lg:top-0 lg:py-4 ml-6 lg:ml-0 lg:pl-6"
                  >
                    <li
                      v-for="megaitem in subitem.children"
                      :key="megaitem.title"
                      class="border-b lg:border-none flex items-center dothover2"
                    >
                      <a href="#">
                        <span
                          class="lg:text-white font-sub-menu font-mon lg:font-bold lg:tracking-widest uppercase lg:dot2 lg:relative"
                          >{{ megaitem.title }}</span
                        >
                      </a>
                    </li>
                  </ul>
                </li>
              </ul>
            </div>
          </transition>
        </li>
      </ul>
      <div>
        <font-awesome-icon
          :icon="['fas', 'search']"
          class="text-white cursor-pointer mr-24 hidden lg:block hover:text-gray-500 transition-all duration-300"
          @click="getCloseSearch"
        />
      </div>
    </nav>

    <Introduce :isClose="isClose" @changeDisplay="isCloseEvent" />

    <SearchBox
      :isCloseSearch="isCloseSearch"
      @changeDisPlaySearch="getCloseSearch"
    />
  </header>
</template>

<script>
import Introduce from '~/components/Introduce.vue'
import SearchBox from '~/components/SearchBox.vue'
export default {
  name: 'NavBar',
  components: { Introduce, SearchBox },
  props: {
    isShowNavBar: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isOpenIntro: false,
      isOpen: false,
      isHover: false,
      isClose: false,
      isCloseSearch: false,
      menu: [
        {
          title: 'Chính sách khách hàng',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          children: [
            {
              title: 'Nội quy mua hàng',
              link: '',
            },
            {
              title: 'Cách thức mua hàng',
              link: '#',
            },
            {
              title: 'Đặc quyền khách vip',
              link: '#',
            },
          ],
        },
        {
          title: 'Nhân vật',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          children: [
            {
              title: 'Huyền thoại',
              link: '#',
            },
            {
              title: 'Đương đại',
              link: '#',
              isOpen: false,
              isOpenMobile: false,
              children: [
                {
                  title: 'Quốc tế',
                  link: '#',
                },
                {
                  title: 'Việt Nam',
                  link: '#',
                },
              ],
            },
          ],
        },
        {
          title: 'Kiến thức vintage',
          isOpen: false,
          isOpenMobile: false,
          isVintage: true,
          link: '#',
          children: [
            {
              title: 'Kiểu dáng',
              link: '#',
            },
            {
              title: 'Chất liệu',
              link: '#',
            },
            {
              title: 'Thương hiệu',
              link: '#',
            },
            {
              title: 'Cảm nhận của dân vintage',
              link: '#',
            },
          ],
        },
        {
          title: 'Shop',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          children: [
            {
              title: 'New arrival',
              link: '#',
            },
            {
              title: 'My cart',
              link: '#',
            },
            {
              title: 'Tracking order',
              link: '#',
            },
          ],
        },
        {
          title: 'Feedback khách hàng',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
        },
      ],
    }
  },
  methods: {
    isCloseEvent() {
      console.log(this.isClose)
      this.isClose = !this.isClose
    },
    getCloseSearch() {
      this.isCloseSearch = !this.isCloseSearch
    },
  },
}
</script>
<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s;
}
.slide-enter, .slide-leave-to /* .fade-leave-active below version 2.1.8 */ {
  transform: translateY(-20px);
  opacity: 0;
}
.move-hover:hover .move {
  animation-name: example;
  animation-duration: 0.7s;
}
.move-hover:hover .move2 {
  animation-name: example2;
  animation-duration: 0.7s;
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

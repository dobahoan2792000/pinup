/* eslint-disable no-unused-vars */
<template>
  <header
    class="lg:flex lg:relative lg:box-border lg:px-10 lg:h-20 lg:counter-reset"
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
      <picture
        class="max-w-md h-4 mx-auto lg:absolute lg:top-1/2 lg:v-align lg:ml-8"
      >
        <img src="/img/logo-standard-dark.png" alt="Flowers" class="h-4" />
      </picture>
    </div>
    <nav
      class="lg:ml-20 lg:flex lg:align-middle lg:h-full lg:w-5/6 lg:justify-between"
      :class="isOpen ? 'block' : 'hidden'"
    >
      <ul class="mx-10 lg:flex lg:my-auto lg:h-full">
        <li
          v-for="(item, index) in menu"
          :key="item.title"
          :class="[
            item.isExpand || item.isFashion || item.isNew ? '' : 'lg:relative',
          ]"
          class="line-hover"
          @mouseenter="item.isOpen = !item.isOpen"
          @mouseleave="item.isOpen = !item.isOpen"
        >
          <a
            :href="item.link"
            class="font-menu py-3 flex justify-between border-b lg:border-0 lg:items-center lg:py-0 lg:px-6 lg:h-full lg:leading-6 lg:font-mon"
            @click="getSubmenu(index)"
            ><span
              class="lg:relative lg:tracking-widest lg:font-medium lg:line"
              >{{ item.title }}</span
            >
            <svg
              class="inline-block my-auto lg:hidden transition-all duration-300"
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
              class="lg:absolute lg:left-0 lg:bg-black lg:top-80 lg:transition-height lg:transition-opacity lg:duration-1000 lg:flex lg:items-center"
              :class="[
                item.isExpand || item.isNew ? 'lg:w-screen' : 'lg:w-56',
                item.isOpenMobile ? 'block' : 'hidden',
                item.isFashion ? 'lg:w-screen' : '',
                item.isNew ? 'lg:justify-center' : '',
              ]"
            >
              <ul
                v-if="item.children && item.children.length"
                :class="[
                  item.isExpand
                    ? 'lg:flex-no-wrap lg:flex lg:justify-around lg:w-full lg:px-32'
                    : 'lg:flex-wrap lg:flex',
                  item.isFashion
                    ? 'lg:flex-wrap lg:flex lg:justify-around lg:px-16 lg:self-start lg:w-2/5'
                    : '',
                  item.isNew ? 'w-5/6' : '',
                ]"
                class="lg:py-6"
              >
                <li
                  v-for="subitem in item.children"
                  :key="subitem.id"
                  :class="[
                    item.isExpand ? 'lg:w-full lg:px-6' : 'dothover',
                    item.isNew
                      ? 'lg:w-1/3 lg:flex lg:flex-no-wrap lg:mb-4 lg:px-4'
                      : 'w-full',
                  ]"
                  @mouseover="item.selectedChild = subitem"
                >
                  <div
                    v-if="item.isNew === true"
                    :class="
                      item.isNew
                        ? 'lg:w-1/3 lg:inline-block lg:overflow-hidden lg:transition-all lg:duration-500 lg:box-border'
                        : ''
                    "
                  >
                    <a href="#">
                      <img
                        :src="subitem.url"
                        :class="subitem.isHover ? 'lg:scale1-05' : ''"
                        alt=""
                        class="hidden lg:block lg:m-0 lg:max-h-full lg:max-w-full lg:align-middle lg:transition-all lg:duration-500"
                        @mouseover="subitem.isHover = !subitem.isHover"
                        @mouseout="subitem.isHover = !subitem.isHover"
                      />
                    </a>
                  </div>
                  <div
                    class="lg:block"
                    :class="
                      item.isNew
                        ? 'lg:w-full lg:ml-6 lg:flex lg:flex-wrap lg:items-center'
                        : ''
                    "
                  >
                    <a
                      :href="subitem.link"
                      class="font-sub-menu font-mon lg:font-bold flex justify-between ml-3 lg:py-1 py-3 border-b lg:border-0 lg:text-white lg:ml-0"
                      :class="[
                        item.isExpand || item.isNew
                          ? ''
                          : 'lg:justify-start lg:px-10',
                        item.isNew ? 'lg:w-full' : '',
                      ]"
                      @click="subitem.isOpen = !subitem.isOpen"
                      ><span
                        class="lg:relative lg:w-full"
                        :class="item.isExpand || item.isNew ? '' : 'lg:dot'"
                      >
                        <span
                          :class="[
                            item.isFeatures
                              ? 'lg:font-vida lg:font-menu font-medium'
                              : '',
                          ]"
                          >{{ subitem.title }}</span
                        >
                      </span>

                      <svg
                        :class="subitem.children ? 'block' : 'hidden'"
                        class="font-menu inline-block my-auto lg:hidden"
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
                          fill="#626262"
                        />
                      </svg>
                    </a>
                    <div
                      v-if="item.isNew === true"
                      :class="item.isNew ? '' : ''"
                      class="hidden lg:block lg:cursor-pointer"
                      @mouseover="subitem.isHover = !subitem.isHover"
                      @mouseout="subitem.isHover = !subitem.isHover"
                    >
                      <a href="#">
                        <span
                          class="lg:text-white lg:font-vida"
                          :class="subitem.isHover ? 'lg:underline' : ''"
                          >{{ subitem.name }}</span
                        >
                      </a>
                    </div>
                  </div>

                  <ul
                    v-if="subitem.children"
                    :class="subitem.isOpen ? 'block' : 'hidden'"
                    class="lg:block"
                  >
                    <li
                      v-for="megaitem in subitem.children"
                      :key="megaitem.title"
                      class="dothover"
                    >
                      <a
                        :href="`${megaitem.link}`"
                        class="lg:font-sub-megamenu lg:font-semibold font-sub-menu flex justify-between ml-8 py-3 lg:py-2 border-b lg:text-white lg:ml-0 font-mon lg:border-0"
                      >
                        <span class="lg:dot lg:relative lg:tracking-widest"
                          ><span>{{ megaitem.title }}</span></span
                        >
                        <svg
                          :class="megaitem.children ? 'block' : 'hidden'"
                          class="font-menu inline-block my-auto lg:hidden"
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
                            fill="#626262"
                          />
                        </svg>
                      </a>
                    </li>
                  </ul>
                </li>
              </ul>
              <div
                v-if="item.isFashion === true && item.selectedChild"
                class="hidden lg:flex lg:flex-no-wrap py-6 lg:pr-6 lg:h-330 lg:pl-10 lg:justify-between lg:mb-10 lg:mt-3"
              >
                <div
                  v-for="image in item.selectedChild.images"
                  :key="image.title"
                  class="lg:flex lg:flex-wrap lg:px-4 lg:w-330"
                >
                  <div
                    class="lg:inline-block lg:box-border lg:w-full lg:h-191 lg:overflow-hidden lg:transition-all lg:duration-200"
                  >
                    <a href="#" class="lg:w-full">
                      <img
                        :src="image.url"
                        class="lg:h-full lg:w-full lg:inline-block transition-all duration-500"
                        :class="image.isHover ? 'lg:scale1-05' : ''"
                        @mouseover="image.isHover = true"
                        @mouseout="image.isHover = false"
                        @click="console(image.isHover)"
                      />
                    </a>
                  </div>
                  <div
                    class="lg:flex lg:flex-wrap lg:number lg:relative lg:pl-12 lg:mt-3 lg:h-24"
                  >
                    <a href=""
                      ><span
                        class="text-white lg:font-sub-menu lg:font-mon lg:font-medium lg:tracking-widest"
                        >{{ image.time }}</span
                      ></a
                    >
                    <a
                      href="#"
                      @mouseover="image.isHover = !image.isHover"
                      @mouseout="image.isHover = !image.isHover"
                    >
                      <span
                        :class="image.isHover ? 'lg:underline' : ''"
                        class="text-white lg:text-base lg:font-vida lg:w-full"
                        >{{ image.title }}</span
                      >
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </transition>
        </li>
      </ul>
      <div class="hidden lg:block">
        <div
          class="flex items-center h-full relative cursor-pointer"
          @mouseover="controlDisplayFollow"
          @mouseout="controlDisplayFollow"
        >
          <div>
            <a
              href="#"
              class="lg:font-mon lg:font-menu inline-block lg:leading-6"
            >
              <svg
                class="inline-block"
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
                  d="M13.418 7.859a.695.695 0 0 1 .978 0a.68.68 0 0 1 0 .969l-3.908 3.83a.697.697 0 0 1-.979 0l-3.908-3.83a.68.68 0 0 1 0-.969a.695.695 0 0 1 .978 0L10 11l3.418-3.141z"
                  fill="#626262"
                />
              </svg>
              FOLLOW ME
            </a>
            <div
              class="absolute w-56 bg-black left-0 box-content top-80 cursor-default transition-all duration-1000"
              :class="
                isOpenFollow
                  ? 'h-40 visible opacity-1'
                  : 'h-0 invisible opacity-0'
              "
            >
              <div class="p-4">
                <div class="flex justify-center mb-8 mt-3">
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
                  >
                    <font-awesome-icon
                      :icon="['fab', 'pinterest-p']"
                      class="text-white text-xs group-hover:text-black"
                    />
                  </a>
                </div>
                <a href="#" class="text-center block"
                  ><span class="text-white line-w relative tracking-widest"
                    >NEWSLETTER SIGN UP</span
                  ></a
                >
              </div>
            </div>
          </div>
          <svg
            class="mt-1 ml-6 text-black"
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
              d="M17.545 15.467l-3.779-3.779a6.15 6.15 0 0 0 .898-3.21c0-3.417-2.961-6.377-6.378-6.377A6.185 6.185 0 0 0 2.1 8.287c0 3.416 2.961 6.377 6.377 6.377a6.15 6.15 0 0 0 3.115-.844l3.799 3.801a.953.953 0 0 0 1.346 0l.943-.943c.371-.371.236-.84-.135-1.211zM4.004 8.287a4.282 4.282 0 0 1 4.282-4.283c2.366 0 4.474 2.107 4.474 4.474a4.284 4.284 0 0 1-4.283 4.283c-2.366-.001-4.473-2.109-4.473-4.474z"
              fill="#626262"
            />
          </svg>
        </div>
      </div>
    </nav>
    <Nuxt />
  </header>
</template>
<script>
export default {
  data() {
    return {
      isOpen: false,
      isHover: false,
      menu: [
        {
          title: 'HOME',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          isExpand: false,
          height: '270px',
          isNew: false,
          selectedChild: null,
          children: [
            {
              id: 1,
              title: 'GALLIANO',
              link: '#',
            },
            {
              id: 2,
              title: 'JACOBS',
              link: '#',
            },
            {
              id: 3,
              title: 'LAGERFELD',
              link: '#',
            },
            {
              id: 4,
              title: 'MCQUEEN',
              link: '#',
            },
            {
              id: 5,
              title: 'GAULTIER',
              link: '#',
            },
            {
              id: 6,
              title: 'HERRERA',
              link: '#',
            },
            {
              id: 7,
              title: 'LANDING',
              link: '#',
            },
          ],
        },
        {
          title: 'FEATURES',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          isFeatures: true,
          isExpand: true,
          height: '394px',
          isNew: false,
          selectedChild: null,
          children: [
            {
              id: 1,
              title: 'BLOCKS & SLIDERS',
              link: '#',
              isOpen: false,
              children: [
                {
                  title: 'BLOCK 1',
                  link: '#',
                },
                {
                  title: 'VIDEO BLOCK 1',
                  link: '#',
                },
                {
                  title: 'VIDEO BLOCK 2',
                  link: '#',
                },
                {
                  title: 'POST CAROUSEL 1',
                  link: '#',
                },
                {
                  title: 'POST CAROUSEL 2',
                  link: '#',
                },
                {
                  title: 'POST CAROUSEL 3',
                  link: '#',
                },
                {
                  title: 'POST CAROUSEL 4',
                  link: '#',
                },
                {
                  title: 'POST CAROUSEL 5',
                  link: '#',
                },
              ],
            },
            {
              id: 2,
              title: 'POST LAYOUTS',
              link: '#',
              isOpen: false,
              children: [
                {
                  title: 'LAYOUT 1',
                  link: '#',
                },
                {
                  title: 'LAYOUT 2',
                  link: '#',
                },
                {
                  title: 'LAYOUT 3',
                  link: '#',
                },
                {
                  title: 'LAYOUT 4',
                  link: '#',
                },
                {
                  title: 'LAYOUT 5',
                  link: '#',
                },
                {
                  title: 'LAYOUT 6',
                  link: '#',
                },
                {
                  title: 'VIDEO LAYOUT 1',
                  link: '#',
                },
              ],
            },
            {
              id: 3,
              title: 'OTHER LAYOUTS',
              link: '#',
              isOpen: false,
              children: [
                {
                  title: 'BLOG MASONRY',
                  link: '#',
                },
                {
                  title: 'STANDARD WITH SIDEBAR',
                  link: '#',
                },
                {
                  title: 'STANDARD WITHOUT SIDEBAR',
                  link: '#',
                },
                {
                  title: 'COMBINED LAYOUT',
                  link: '#',
                },
                {
                  title: 'CATEGORY FILTER',
                  link: '#',
                },
                {
                  title: 'PAGINATION EXAMPLES',
                  link: '#',
                },
              ],
            },
            {
              id: 4,
              title: 'POST TYPES',
              link: '#',
              isOpen: false,
              children: [
                {
                  title: 'STANDARD',
                  link: '#',
                },
                {
                  title: 'GALLERY',
                  link: '#',
                },
                {
                  title: 'LINK',
                  link: '#',
                },
                {
                  title: 'QUOTE',
                  link: '#',
                },
                {
                  title: 'AUDIO',
                  link: '#',
                },
                {
                  title: 'VIDEO',
                  link: '#',
                },
              ],
            },
          ],
        },
        {
          title: 'FASHION',
          isOpen: false,
          isOpenMobile: false,
          height: '376px',
          link: '#',
          isFashion: true,
          isNew: false,
          selectedChild: null,
          children: [
            {
              id: 1,
              title: 'FASHION',
              link: '#',
              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/Fashion/dd-post-1-306x191.jpg',
                  time: '2 YEARS AGO',
                  title: 'Hair Masks to Repair Summer Sun Damage',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Fashion/h1-video-post-5-306x191.jpg',
                  time: '2 YEARS AGO',
                  title: 'Photographers, Artists And Curators To Watch',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Fashion/dd-post-2-306x191.jpg',
                  time: '2 YEARS AGO',
                  title: 'Made In The Shade: The Season’s Best Sunglasses',
                },
              ],
            },
            {
              id: 2,
              title: 'EDITORIAL',
              link: '#',

              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/Editorial/1.jpg',
                  time: '8 MONTHS AGO',
                  title:
                    'Day To Night Outfit – How To Transform Your Day Look For A Night Out!',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Editorial/2.jpg',
                  time: '2 YEARS AGO',
                  title: 'Go Behind-The-Scenes At The Paris Fashion Week',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Editorial/3.jpg',
                  time: '2 YEARS AGO',
                  title:
                    'Blake And Gigi Hadid Hung Out Last Night And It Was Precious',
                },
              ],
            },
            {
              id: 3,
              title: 'GLAMOUR',
              link: '#',

              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/Glamour/1.jpg',
                  time: '2 YEARS AGO',
                  title: '15 Office-Friendly Summer Outfit Ideas',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Glamour/2.jpg',
                  time: '2 YEARS AGO',
                  title: '20 Chunky Knit Sweaters To Cozy Up In This Winter',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Glamour/3.jpg',
                  time: '2 YEARS AGO',
                  title: 'High Brow: The Best Celebrity Eyebrows Shape',
                },
              ],
            },
            {
              id: 4,
              title: 'STYLISH',
              link: '#',

              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/Stylish/1.jpg',
                  time: '2 YEARS AGO',
                  title: 'All The Best Beauty Looks From The 2018 Met Gala',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Stylish/2.jpg',
                  time: '2 YEARS AGO',
                  title: 'Self-Tanners That Will Make You Look Amazing',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Stylish/3.jpg',
                  time: '2 YEARS AGO',
                  title: 'High School Teacher Who Models In His Spare Time',
                },
              ],
            },
            {
              id: 5,
              title: 'BUSINESS',
              link: '#',

              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/Business/1.jpg',
                  time: '2 YEARS AGO',
                  title:
                    'The Best Street Style At London Fashion Week Fall 2018',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Business/2.jpg',
                  time: '2 YEARS AGO',
                  title:
                    'The Best Street Style At Paris Fashion Week Fall 2018',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/Business/3.jpg',
                  time: '2 YEARS AGO',
                  title: 'The Role Of The Designer Is That Of A Good Host',
                },
              ],
            },
            {
              id: 6,
              title: 'LIFESTYLE',
              link: '#',

              images: [
                {
                  isHover: false,
                  url: '/img/Fashion/LifeStyle/1.jpg',
                  time: '8 MONTHS AGO',
                  title:
                    'Fashion News: All The Celebs At Coachella 2018 Right Now',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/LifeStyle/2.jpg',
                  time: '8 MONTHS AGO',
                  title:
                    'Fashion Needs A New Business Model. Speed Is The Answer.',
                },
                {
                  isHover: false,
                  url: '/img/Fashion/LifeStyle/3.jpg',
                  time: '8 MONTHS AGO',
                  title: 'Meet The Boys Behind The Coolest Party In Dubai',
                },
              ],
            },
          ],
        },
        {
          title: 'PAGES',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          height: '238px',
          isNew: false,
          selectedChild: null,
          children: [
            {
              id: 1,
              title: 'ABOUT US',
              link: '#',
            },
            {
              id: 2,
              title: 'MEET THE TEAM',
              link: '#',
            },
            {
              id: 3,
              title: 'MY POSTS',
              link: '#',
            },
            {
              id: 4,
              title: 'ARCHIVE',
              link: '#',
            },
            {
              id: 5,
              title: 'CONTACT US',
              link: '#',
            },
            {
              id: 6,
              title: 'TYPOGRAPHY',
              link: '#',
            },
          ],
        },
        {
          title: 'SHOP',
          link: '#',
          isOpen: false,
          isOpenMobile: false,
          height: '206px',
          isNew: false,
          selectedChild: null,
          children: [
            {
              id: 1,
              title: 'PRODUCT LIST',
              link: '#',
            },
            {
              id: 2,
              title: 'PRODUCT SINGLE',
              link: '#',
            },
            {
              id: 3,
              title: 'MY ACCOUNT',
              link: '#',
            },
            {
              id: 4,
              title: 'CART',
              link: '#',
            },
            {
              id: 5,
              title: 'CHECK OUT',
              link: '#',
            },
          ],
        },
        {
          title: 'NEW',
          isOpen: false,
          isOpenMobile: false,
          isNew: true,
          link: '#',
          height: '370px',
          selectedChild: null,
          children: [
            {
              id: 1,
              url: '/img/New/1.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'Hair Masks to Repair Summer Sun Damage',
            },
            {
              id: 2,
              url: '/img/New/2.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'Photographers, Artists and Curators to Watch',
            },
            {
              id: 3,
              url: '/img/New/3.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'Made In the Shade: The Season’s Best Sunglasses',
            },
            {
              id: 4,
              url: '/img/New/4.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'The Best Spring Street Style from New York',
            },
            {
              id: 5,
              url: '/img/New/5.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'Runway: The Ultimate Wardrobe Updates',
            },
            {
              id: 6,
              url: '/img/New/6.jpg',
              isHover: false,
              title: 'FASHION',
              name: 'The Best Dressed: From Casual Chic to White Hot',
            },
            {
              id: 7,
              url: '/img/New/7.jpg',
              isHover: false,
              title: 'STYLISH',
              name: 'All The Best Beauty Looks From The 2018 Met Gala',
            },
            {
              id: 8,
              url: '/img/New/8.jpg',
              isHover: false,
              title: 'STYLISH',
              name: 'Self-Tanners That Will Make You Look Amazing',
            },
            {
              id: 9,
              url: '/img/New/9.jpg',
              isHover: false,
              title: 'STYLISH',
              name: 'High School Teacher Who Models in His Spare Time',
            },
          ],
        },
      ],
      isOpenFollow: false,
    }
  },
  methods: {
    controlDisplayFollow() {
      this.isOpenFollow = !this.isOpenFollow
      return this.isOpenFollow
    },
    getSubmenu(index) {
      for (let i = 0; i < this.menu.length; i++) {
        if (i === index) {
          this.menu[i].isOpenMobile = !this.menu[i].isOpenMobile
        } else {
          this.menu[i].isOpenMobile = false
        }
      }
    },
  },
}
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 1s;
}
.slide-enter, .slide-leave-to /* .fade-leave-active below version 2.1.8 */ {
  transform: translateY(-20px);
  opacity: 0;
}
</style>

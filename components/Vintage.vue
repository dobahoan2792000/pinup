<template>
  <div class="flex justify-center">
    <!-- control width -->
    <div class="w-11/12 sm:w-9/12 lg:w-10/12 lg:flex">
      <!-- article -->
      <div class="relative lg:w-9/12 lg:mx-6">
        <!-- img -->
        <div>
          <a href="#"><img src="/img/Vintage/img1.jpg" alt="avatavintage" class="inline-block" /></a>
        </div>
        <div class="relative px-3 lg:px-6 xl:px-12 top-negative-77">
          <div class="bg-white px-12 py-6">
            <div class="sm:inline-block">
              <a
                href="#"
                class="font-mon font-sub-menu uppercase relative dot-black"
                >August 22, 2020</a
              >
            </div>
            <div class="sm:inline-block sm:ml-6">
              <span class="font-mon font-sub-menu uppercase">By</span>
              <a
                href="#"
                class="font-mon font-sub-menu uppercase relative dot-black"
                >Meo cung</a
              >
            </div>
            <div class="md:inline-block md:ml-6">
              <a
                href="#"
                class="font-mon font-sub-menu uppercase relative dot-black"
                >0 Comments</a
              >
              <a href="#" class="font-mon font-sub-menu uppercase ml-5"
                >Likes</a
              >
            </div>
            <div>
              <h2>
                <a href="#" class="font-vida text-2xl md:text-3xl lg:text-4xl">
                  CẦN GÌ PHẢI PHONG CÁCH – MẶC CHO VUI ẤY MÀ
                </a>
              </h2>
              <div>
                <p class="font-mon text-sm text-gray-700 three-dot">
                  Phong cách của mình là chẳng có phong cách gì sất. Mình không
                  nghĩ nhất định phải thanh lịch, cá tính, dịu dàng, ngây thơ,
                  hay cổ điển vintage. Mình có thể là tất cả nếu muốn, làm sao
                  bắt
                </p>
              </div>
            </div>
            <div class="mt-6 md:flex md:justify-between">
              <div
                class="w-full sm:w-5/12 md:w-1/3 px-6 lg:w-1/3 xl:w-1/4 py-3 border-black border overflow-hidden relative move-hover cursor-pointer"
                @mouseenter="isHoverReadMore = !isHoverReadMore"
                @mouseleave="isHoverReadMore = !isHoverReadMore"
              >
                <a
                  href="#"
                  class="w-full h-full flex justify-center items-center"
                >
                  <span
                    class="font-mon font-menu uppercase z-10"
                    :class="[isHoverReadMore ? 'move' : 'move2']"
                    >Read more</span
                  >
                  <div
                    class="w-full h-16 absolute transition-all duration-500 bg-black"
                    :class="[isHoverReadMore ? 'top--70' : 'top-40']"
                  ></div>
                  <span
                    class="w-full absolute bottom-0 transition-all duration-100 delay-200 bg-black"
                    :class="[isHoverReadMore ? 'h-3px' : 'h-0']"
                  ></span>
                </a>
              </div>
              <div class="flex mt-4 md:mt-0">
                <div
                  class="inline-flex justify-center border border-black mr-3 duration-500 transition-opacity"
                  :class="
                    isHoverSocial
                      ? 'opacity-100 visible'
                      : 'opacity-0 invisible'
                  "
                >
                  <a
                    href="#"
                    class="py-3 px-4 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-300"
                    :class="
                      isHoverSocial
                        ? 'opacity-100 visible'
                        : 'opacity-0 invisible'
                    "
                  >
                    <font-awesome-icon
                      :icon="['fab', 'facebook-f']"
                      class="text-xs group-hover:text-white"
                    />
                  </a>

                  <a
                    href="#"
                    class="py-3 px-4 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-200"
                    :class="
                      isHoverSocial
                        ? 'opacity-100 visible'
                        : 'opacity-0 invisible'
                    "
                  >
                    <font-awesome-icon
                      :icon="['fab', 'twitter']"
                      class="text-xs group-hover:text-white"
                    />
                  </a>
                  <a
                    href="#"
                    class="py-3 px-4 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-100"
                    :class="
                      isHoverSocial
                        ? 'opacity-100 visible'
                        : 'opacity-0 invisible'
                    "
                  >
                    <font-awesome-icon
                      :icon="['fab', 'instagram']"
                      class="text-xs group-hover:text-white"
                    />
                  </a>
                  <a
                    href="#"
                    class="py-3 px-4 flex items-center group hover:bg-black transition-opacity duration-100"
                    :class="
                      isHoverSocial
                        ? 'opacity-100 visible'
                        : 'opacity-0 invisible'
                    "
                  >
                    <font-awesome-icon
                      :icon="['fab', 'pinterest-p']"
                      class="text-xs group-hover:text-white"
                    />
                  </a>
                </div>
                <div class="flex items-center mr-3">
                  <font-awesome-icon
                    :icon="['fas', 'share-alt']"
                    @mouseover="isHoverSocial = !isHoverSocial"
                    @mouseout="isHoverSocial = !isHoverSocial"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- aside -->
      <aside class="lg:w-3/12 lg:mx-2">
        <!-- search -->
        <div>
          <form action="" class="relative">
            <input
              type="text"
              placeholder="Search*"
              class="font-mon text-xs w-full py-3 outline-none"
              @click="isSearch = !isSearch"
              @blur="isSearch =!isSearch"
            />
            <button class="absolute valign right-0 outline-none mx-3">
              <font-awesome-icon
                :icon="['fas', 'search']"
                class="text-gray-700"
              />
            </button>
            <span
              class="absolute left-0 bottom-0 w-full bg-gray-500 transition-all duration-200"
              :class="isSearch ? 'h-3px' : 'h-1px'"
            ></span>
          </form>
        </div>
        <!-- img -->
        <div class="mt-24">
          <img src="/img/Vintage/img2.png" alt="" />
        </div>
        <!-- categories -->
        <div class="mt-16">
          <div>
            <h5
              class="font-mon text-xs tracking-widest py-4 px-5 bg-black text-white uppercase"
            >
              Categories
            </h5>
          </div>
          <ul class="mt-6">
            <li v-for="category in listCategories" :key="category" class="py-1">
              <a href="#"
                ><span class="font-vida text-lg relative dot-black-category">{{
                  category
                }}</span></a
              >
            </li>
          </ul>
        </div>
        <div class="relative mt-10">
          <div
            class="w-full overflow-hidden"
            @mouseenter="isHoverNewSpring = !isHoverNewSpring"
            @mouseleave="isHoverNewSpring = !isHoverNewSpring"
          >
            <a href="#">
              <img
                src="/img/Vintage/img3.jpg"
                alt="fashion"
                class="transition-all duration-500"
                :class="isHoverNewSpring ? 'scale1-05' : ''"
              />
            </a>
          </div>
          <div class="relative px-5 top-negative-77">
            <div class="bg-white px-6 py-6 text-center">
              <div class="mb-2">
                <a
                  href="#"
                  class="font-mon font-sub-menu uppercase relative dot-black tracking-widest"
                  >April 26, 2018</a
                >
                <a
                  href="#"
                  class="font-mon font-sub-menu uppercase ml-5 tracking-widest"
                  >Fashion</a
                >
              </div>
              <div class="flex justify-center">
                <div
                  @mouseenter="isHoverNewSpring = !isHoverNewSpring"
                  @mouseleave="isHoverNewSpring = !isHoverNewSpring"
                >
                  <a
                    href="#"
                    class="font-vida text-xl w-4/5 transition-all duration-200"
                    :class="isHoverNewSpring ? 'underline' : ''"
                  >
                    See New Spring Editorial
                  </a>
                </div>
              </div>
              <p class="font-mon text-xs text-gray-800 uppercase mt-2">
                By <a href="#">Pinupadmin</a>
              </p>
            </div>
          </div>
        </div>
        <!-- popular stories -->
        <div>
          <div>
            <h5
              class="font-mon text-xs tracking-widest py-4 px-5 bg-black text-white uppercase"
            >
              Popular stories
            </h5>
          </div>
          <div class="mt-8">
            <div
              v-for="story in polularStories"
              :key="story.url"
              class="flex items-center py-3"
            >
              <div
                class="w-1/3 mr-2 overflow-hidden"
                @mouseenter="story.isHoverStory = !story.isHoverStory"
                @mouseleave="story.isHoverStory = !story.isHoverStory"
              >
                <a href="#"
                  ><img
                    :src="story.url"
                    alt=""
                    class="transition-all duration-500"
                    :class="story.isHoverStory ? 'scale1-05' : ''"
                /></a>
              </div>
              <div class="w-2/3 ml-2">
                <div>
                  <a
                    href="#"
                    class="font-mon font-sub-menu uppercase tracking-widest"
                    >{{ story.kind }}</a
                  >
                </div>
                <div
                  @mouseenter="story.isHoverStory = !story.isHoverStory"
                  @mouseleave="story.isHoverStory = !story.isHoverStory"
                >
                  <a
                    href="#"
                    class="font-vida text-lg transition-all duration-200"
                    :class="story.isHoverStory ? 'underline' : ''"
                    >{{ story.title }}</a
                  >
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- social -->
        <div>
          <div class="flex mt-6 justify-center">
            <div>
              <div class="inline-flex justify-center border border-black">
                <a
                  href="#"
                  class="p-5 border-r border-black flex items-center group hover:bg-black"
                >
                  <font-awesome-icon
                    :icon="['fab', 'facebook-f']"
                    class="text-xs group-hover:text-white"
                  />
                </a>

                <a
                  href="#"
                  class="p-5 border-r border-black flex items-center group hover:bg-black"
                >
                  <font-awesome-icon
                    :icon="['fab', 'twitter']"
                    class="text-xs group-hover:text-white"
                  />
                </a>
                <a
                  href="#"
                  class="p-5 border-r border-black flex items-center group hover:bg-black"
                >
                  <font-awesome-icon
                    :icon="['fab', 'instagram']"
                    class="text-xs group-hover:text-white"
                  />
                </a>
                <a href="#" class="p-5 flex items-center group hover:bg-black">
                  <font-awesome-icon
                    :icon="['fab', 'pinterest-p']"
                    class="text-xs group-hover:text-white"
                  />
                </a>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-16 h-6 w-full border border-black"></div>
        <!-- tags -->
        <div class="mt-10">
          <div class="mb-8">
            <h5
              class="font-mon text-xs tracking-widest py-4 px-5 bg-black text-white uppercase"
            >
              Tags
            </h5>
          </div>
          <div class="flex flex-wrap mt-6">
            <a
              v-for="tag in tags"
              :key="tag.url"
              :href="tag.url"
              class="px-2 py-2 font-mon font-sub-menu tracking-widest uppercase border border-black hover:bg-black hover:text-white"
              >{{ tag.title }}</a
            >
          </div>
        </div>
      </aside>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHoverNewSpring: false,
      isHoverSocial: false,
      isHoverReadMore: false,
      isSearch: false,
      listCategories: [
        'Beauty',
        'Business',
        'Clothing',
        'Design',
        'Editorial',
        'Fashion',
        'Glamour',
        'Kiến thức vintage',
        'Lifestyle',
        'Stylish',
        'Summer',
        'Uncategorized',
      ],
      polularStories: [
        {
          url: '/img/Vintage/popular-stories-1.jpg',
          title: "What we're Loving This Week",
          kind: 'lifestyle',
          isHoverStory: false,
        },
        {
          url: '/img/Vintage/popular-stories-2.jpg',
          title: 'Meet The Young New Designers',
          kind: 'lifestyle',
          isHoverStory: false,
        },
        {
          url: '/img/Vintage/popular-stories-3.jpg',
          title: 'Ten Ways to Wear Leopard Print',
          kind: 'lifestyle',
          isHoverStory: false,
        },
      ],
      tags: [
        {
          url: '#',
          title: 'Beauty',
        },
        {
          url: '#',
          title: 'Classy',
        },
        {
          url: '#',
          title: 'Cool',
        },
        {
          url: '#',
          title: 'Design',
        },
        {
          url: '#',
          title: 'Fashion',
        },
        {
          url: '#',
          title: 'Look',
        },
        {
          url: '#',
          title: 'Model',
        },
        {
          url: '#',
          title: 'Photoart',
        },
        {
          url: '#',
          title: 'Retro',
        },
        {
          url: '#',
          title: 'Styles',
        },
        {
          url: '#',
          title: 'Trend',
        },
      ],
    }
  },
}
</script>
<style scoped>
.top-negative-77 {
  top: -77px;
}
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

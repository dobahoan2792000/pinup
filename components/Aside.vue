<template>
  <aside class="lg:w-3/12 lg:mr-6">
    <!-- search -->
    <div>
      <form action="" class="relative">
        <input
          type="text"
          placeholder="Search*"
          class="font-mon text-xs w-full py-3 outline-none"
          @click="isSearch = !isSearch"
          @blur="isSearch = !isSearch"
        />
        <button class="absolute valign right-0 outline-none mx-3">
          <font-awesome-icon :icon="['fas', 'search']" class="text-gray-700" />
        </button>
        <span
          class="absolute left-0 bottom-0 w-full bg-gray-500 transition-all duration-200"
          :class="isSearch ? 'h-3px' : 'h-1px'"
        ></span>
      </form>
    </div>
    <!-- img -->
    <div class="mt-24">
      <a href="#"><img src="/img/Vintage/img2.png" alt="" /></a>
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
        <div class="bg-white px-4 py-6 text-center">
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
</template>

<script>
export default {
  data() {
    return {
      isHoverNewSpring: false,
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

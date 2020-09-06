<template>
  <div class="flex justify-center">
    <div class="w-10/12 md:w-11/12 lg:flex">
      <div class="mb-6 lg:w-9/12 lg:px-12 xl:px-16">
        <div>
          <img src="/img/article/h1-post-6.jpg" />
        </div>
        <!-- content -->
        <div class="px-6 md:px-16 mt-8">
          <div>
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
          </div>
          <div>
            <h2 class="font-vida text-2xl lg:text-4xl my-2">
              Fashion News: The Best Catwalk Shoes This Season
            </h2>
            <p class="font-mon text-sm lg:text-xs text-gray-700 mt-6">
              Sed non mauris vitae erat consequat. Proin gravida nibh vel velit
              auctor aliquet. Aenean sollicitudin, lom quis bibenm auctor, nisi
              elit consequat ipsum, nec sagittis sem nibh id elit. Duis sed odio
              sit amet nibh vuutate cursus a sit amet maorbi accumsan ipsum
              velit. Lorem ipsum dolor sit amet velit auctor aliquet. Aenean
              sollicitudin, lorem quis bibendum auctor, nisi elit consequat
              ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh
              vulputate cursus a sit amet maorbi accumsan ipsum velit. Nam nec
              tellus a odio tincidunt auctor a ornare odio. Sed non mauris vitae
              erat consequat auctor eu in elit. Classaptent taciti sociosqu ad
              litora torquent per conubia nostra, per inceptos himenaeos. Mauris
              in erat justo. Nullam ac urna eu felis dapibus condimentum sit
              amet a augue. Sed non neque elit. Sed ut imperdiet nisi. Proin
              condimentum fermentum nunc. Etiam pharetra, erat sed fermentum
              feugiat, velit mauris egesta lorem ispsum dolor sit amet. Proin
              gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lom
              quis bibenm auctor, nisi elit consequat ipsum, nec sagittis sem
              nibh id elit. Duis sed odio sit amet nibh vuutate cursus a sit
              amet maorbi accumsan ipsum velit lorem ipsum dolor sit amet. Velit
              auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor,
              nisi elit consequat ipsum, nec sagittis sem nibh id elit. Duis sed
              odio sit amet nibh vulputate cursus a sit amet maorbi accumsan
              ipsum velit. Nam nec tellus a odio tincidunt auctor a ornare odio.
              Sed non mauris vitae erat consequat auctor eu in elit. Classaptent
              taciti sociosqu ad litora torquent per conubia nostra, per
              inceptos himenaeos. Mauris in erat justo. Nullam ac urna eu felis
              dapibus condimentum sit amet a augue. Sed non neque elit. Sed ut
              imperdiet nisi. Proin condimentum fermentum nunc. Etiam pharetra,
              erat sed fermentum feugiat, velit mauris egesta.
            </p>
            <blockquote class="quote py-3">
              <p
                class="table-cell align-middle font-vida text-2xl lg:text-xl border-l border-black pl-3 py-3"
              >
                Designers can create normalcy out of chaos; they cany out
                ommunic ate ideas through the organising and manip
              </p>
            </blockquote>
            <p class="font-mon text-sm text-gray-700 lg:text-xs">
              Sed non mauris vitae erat consequat. Velit auctor aliquet. Aenean
              sollicitudin, lorem quis bibendum auctor, nisi elit consequat
              ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh
              vulputate cursus a sit amet maorbi accumsan ipsum velit. Nam nec
              tellus a odio tincidunt auctor a ornare odio. Sed non mauris vitae
              erat consequat auctor eu in elit. Classaptent taciti sociosqu ad
              litora torquent per conubia nostra, per inceptos himenaeos. Mauris
              in erat justo. Nullam ac urna eu felis dapibus condimentum sit
              amet a augue. Sed non neque elit. Sed ut imperdiet nisi. Proin
              condimentum fermentum nunc. Etiam pharetra, erat sed fermentum
              feugiat, velit mauris egesta.
            </p>
          </div>
          <div class="mt-12 md:flex md:justify-between md:mt-16">
            <div class="flex flex-wrap">
              <a
                v-for="tag in tags"
                :key="tag.url"
                :href="tag.url"
                class="px-2 py-2 font-mon font-sub-menu tracking-widest uppercase border border-black hover:bg-black hover:text-white"
                >{{ tag.title }}</a
              >
            </div>
            <div
              class="flex mt-4 md:mt-0"
              @mouseover="isHoverSocial = !isHoverSocial"
              @mouseout="isHoverSocial = !isHoverSocial"
            >
              <div
                class="inline-flex justify-center border border-black mr-3 duration-500 transition-opacity"
                :class="
                  isHoverSocial
                    ? 'opacity-100 visible'
                    : 'opacity-0 invisible w-0'
                "
              >
                <a
                  href="#"
                  class="py-2 px-3 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-300"
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
                  class="py-2 px-3 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-200"
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
                  class="py-2 px-3 border-r border-black flex items-center group hover:bg-black transition-opacity duration-100 delay-100"
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
                  class="py-2 px-3 flex items-center group hover:bg-black transition-opacity duration-100"
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
                <font-awesome-icon :icon="['fas', 'share-alt']" />
              </div>
            </div>
          </div>
        </div>
        <!-- infor writer -->
        <div class="mt-20 px-4 pb-6 md:flex">
          <div class="h-48 md:h-40 md:w-full">
            <img src="/img/article/h2-post-6.jpg" class="h-full" />
          </div>
          <div class="mt-6 md:mt-0">
            <a href="#"><p class="font-vida text-2xl mb-3">Anne Green</p></a>
            <p class="font-mon text-sm text-gray-900">
              Lorem ipsum dolor sit amet. Proin gravida nibh vel veli auctor
              aliquet ipsum. Proin gravida nibh vel veli auctor aliquet. Aenean
              proin gravida nibh.
            </p>
            <p class="relative font-night text-4xl bg-pink py-6">
              Fashion blogger
            </p>
          </div>
        </div>
        <div class="h-1px w-full bg-gray-300"></div>
        <!-- next,previous -->
        <div class="flex justify-between mt-4">
          <a
            href="#"
            class="font-mon text-xs uppercase relative py-1 group"
            @mouseover="isHoverPrevious = !isHoverPrevious"
            @mouseout="isHoverPrevious = !isHoverPrevious"
            >Previous post
            <span
              class="absolute w-full bg-black bottom-0 left-0 transition-all duration-150"
              :class="isHoverPrevious ? 'h-3px' : 'h-1px'"
            ></span>
          </a>
          <a
            href="#"
            class="font-mon text-xs uppercase relative py-1"
            @mouseover="isHoverNext = !isHoverNext"
            @mouseout="isHoverNext = !isHoverNext"
            >Next post
            <span
              class="absolute w-full bg-black bottom-0 left-0 transition-all duration-150"
              :class="isHoverNext ? 'h-3px' : 'h-1px'"
            ></span>
          </a>
        </div>
        <!-- related -->
        <div class="mt-16">
          <h5
            class="text-xs font-mon uppercase relative overflow-hidden line-relate tracking-widest mb-6"
          >
            Related posts
          </h5>
          <div class="md:flex">
            <div v-for="post in posts" :key="post.title" class="mb-6 px-2">
              <div class="mb-4">
                <img :src="post.url" alt="post" />
              </div>
              <div>
                <a
                  href="#"
                  class="font-mon font-sub-menu uppercase relative dot-black"
                  >{{ post.style }}</a
                >
                <a href="#" class="font-mon font-sub-menu uppercase ml-5">{{
                  post.day
                }}</a>
              </div>
              <div>
                <a href="#" class="font-vida text-lg">{{ post.title }}</a>
              </div>
            </div>
          </div>
        </div>
        <!-- comment -->
        <div>
          <h5
            class="text-xs font-mon uppercase relative overflow-hidden line-relate tracking-widest mb-6"
          >
            Related posts
          </h5>
          <textarea
            name="comment"
            idcomment
            rows="8"
            placeholder="message*"
            class="w-full border border-gray-300 px-4 py-3 outline-none font-mon text-sm"
          ></textarea>
          <!-- Name,email -->
          <div class="w-full flex justify-between mt-8">
            <div class="width-47 border-b border-black">
              <label class="font-mon text-sm text-gray-700 block" for="name"
                >Name *</label
              >
              <input
                id="name"
                type="text"
                class="w-full py-3 outline-none text-sm"
              />
            </div>
            <div class="width-47 border-b border-black">
              <label for="email" class="font-mon text-sm text-gray-700 block"
                >Email *</label
              >
              <input
                id="email"
                type="text"
                class="w-full py-3 outline-none text-sm"
              />
            </div>
          </div>
          <p class="mt-4">
            <input id="check" type="checkbox" />
            <label for="check" class="font-mon text-sm text-gray-700"
              >Save my name, email, and website in this browser for the next
              time I comment.</label
            >
          </p>
          <div class="flex justify-end mt-3">
            <input
              type="submit"
              value="Submit"
              class="px-6 py-3 border bg-white border-black font-mon text-xs uppercase tracking-widest cursor-pointer effect"
            />
          </div>
        </div>
      </div>
      <Aside />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHoverSocial: false,
      isHoverPrevious: false,
      isHoverNext: false,
       tags: [
        {
          url: '#',
          title: 'Beauty',
        },
        {
          url: '#',
          title: 'Design',
        },
        {
          url: '#',
          title: 'Cool',
        },
      ],
      posts: [
        {
          url: '/img/article/posts/1.jpg',
          style: 'lifestyle',
          day: 'april 12, 2019',
          title: 'Fashion News: all the Celebs at Coachella 2018 Right Now',
        },
        {
          url: '/img/article/posts/2.jpg',
          style: 'lifestyle',
          day: 'april 12, 2019',
          title: 'Fashion Needs a New Business Model. Speed is the Answer.',
        },
        {
          url: '/img/article/posts/3.jpg',
          style: 'lifestyle',
          day: 'april 12, 2019',
          title: 'Meet the Boys Behind the Coolest Party in Dubai',
        },
      ],
    }
  },
}
</script>
<style scoped>
.line-relate::after {
  position: absolute;
  content: '';
  height: 1px;
  width: 100%;
  top: 50%;
  background-color: #d7d7d7;
  -webkit-transform: translateY(-50%);
  -moz-transform: translateY(-50%);
  transform: translateY(-50%);
  margin-left: 10px;
}
</style>

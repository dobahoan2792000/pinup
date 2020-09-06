<template>
  <div class="flex justify-center">
    <!-- control width -->
    <div class="w-11/12 sm:w-9/12 lg:w-10/12 xl:w-11/12 lg:flex">
      <!-- article -->
      <div class="relative lg:w-9/12 lg:mx-20">
        <!-- img -->
        <div class="xl:mr-6">
          <a href="#"><img src="/img/Vintage/img1.jpg" alt="avatavintage" /></a>
        </div>
        <div class="relative px-3 lg:px-6 top-negative-77">
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
              <div class="flex mt-4 md:mt-0"  @mouseover="isHoverSocial = !isHoverSocial"
                    @mouseout="isHoverSocial = !isHoverSocial">
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

                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- aside -->
      <Aside />
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
    }
  },
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

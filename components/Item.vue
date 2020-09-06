<template>
  <div class="w-full flex justify-center">
    <div class="w-9/12 md:w-11/12 lg:w-11/12">
      <div class="w-full lg:flex lg:flex-no-wrap  md:px-4">
        <!-- ảnh -->
        <div class="w-full flex flex-wrap lg:w-6/12">
          <div class="w-full flex flex-wrap md:relative md:justify-end">
            <div
              v-for="(img, index) in item.images"
              :key="img.url"
              :class="[
                index === 0
                  ? 'w-full px-2 md:order-last md:w-9/12'
                  : 'mt-4 w-1/3 px-2 md:absolute md:mt-0',
                index === 1 ? 'md:top-0 md:left-0 md:w-3/12' : '',
                index === 2 ? 'md:valign md:left-0 md:w-3/12' : '',
                index === 3 ? 'md:bottom-0 md:left-0 md:w-3/12' : '',
              ]"
            >
              <img
                :src="img.url"
                alt=""
                class="w-full h-full cursor-pointer"
                @click="selectedNumber = index"
              />
            </div>
          </div>
        </div>
        <!-- Thông tin sản phẩm -->
        <div
          class="lg:w-6/12 flex flex-wrap lg:pl-20 lg:block px-2 lg:px-0 mt-4 lg:mt-0"
        >
          <div class="w-full">
            <h2 class="text-3xl font-vida mb-1">{{ item.name }}</h2>
            <div class="mb-2">
              <font-awesome-icon :icon="['fas', 'star']" />
              <font-awesome-icon :icon="['fas', 'star']" />
              <font-awesome-icon :icon="['fas', 'star']" />
              <font-awesome-icon :icon="['fas', 'star']" />
              <font-awesome-icon :icon="['far', 'star']" />
            </div>
            <span class="font-vida text-xl">{{ item.price }}₫</span>
            <div class="mt-6">
              <p
                class="font-mon text-sm lg:text-xs text-gray-700"
              >
                {{ item.infor }}
              </p>
            </div>
          </div>
          <div class="flex items-center relative mt-4 w-full lg:mt-6">
            <div class="count-box-sm border border-black relative">
              <div
                class="absolute h-full width-38 border-r border-black box-border flex items-center justify-center"
              >
                <span>1</span>
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
            <div>
              <div
                class="px-12 py-3 border-black border overflow-hidden relative move-hover ml-8 cursor-pointer"
                @mouseenter="isHover = !isHover"
                @mouseleave="isHover = !isHover"
              >
                <a
                  href="#"
                  class="w-full h-full flex justify-center items-center"
                >
                  <span
                    class="font-mon font-menu uppercase"
                    :class="[
                      isHover ? 'move' : 'move2',
                      selectedNumber >= 0 ? '' : 'z-10',
                    ]"
                    >Add to cart</span
                  >
                  <div
                    class="w-full h-16 absolute transition-all duration-500 bg-black"
                    :class="[isHover ? 'top--70' : 'top-40']"
                  ></div>
                  <span
                    class="w-full absolute bottom-0 transition-all duration-100 delay-200 bg-black"
                    :class="[isHover ? 'h-3px' : 'h-0']"
                  ></span>
                </a>
              </div>
            </div>
          </div>
          <div class="mt-6">
            <div>
              <span class="font-vida text-lg">SKU:</span>
              <span class="font-mon text-sm text-gray-700">002</span>
            </div>
            <div>
              <span class="font-vida text-lg">Category:</span>
              <a href="#"
                ><span class="font-mon text-sm text-gray-700">Clothes</span></a
              >
            </div>
            <div>
              <span class="font-vida text-lg">Tags:</span>
              <a href="#" class="font-mon text-sm text-gray-700">Design</a
              ><span class="font-vida text-lg">,</span>
              <a href="#" class="font-mon text-sm text-gray-700">Ideas</a
              ><span class="font-vida text-lg">,</span>
              <a href="#" class="font-mon text-sm text-gray-700">New</a
              ><span class="font-vida text-lg">,</span>
              <a href="#" class="font-mon text-sm text-gray-700">Pastel</a>
            </div>
          </div>
        </div>
      </div>

      <div class="w-full px-2 md:px-4">
        <div
          class="w-full mt-8 flex flex-wrap md:flex-no-wrap border-b border-gray-300"
        >
          <span
            v-for="(infor, index) in moreInfor"
            :key="infor.title"
            class="py-3 first:pr-3 first:px-0 font-mon text-sm letter-space-15 uppercase relative cursor-pointer"
            :class="index != 0 ? 'px-3' : 'pr-3'"
            @click="getIndex(index)"
            @mouseover="infor.isHover = !infor.isHover"
            @mouseout="infor.isHover = !infor.isHover"
            >{{ infor.title }}
            <span
              class="w-full h-0 absolute bg-black bottom-0 left-0 transition-all duration-200"
              :class="infor.isChoose || infor.isHover ? 'h-3px' : ''"
            ></span>
          </span>
        </div>
        <div class="mt-8">
          <!-- Description -->
          <p
            v-if="moreInfor[0].isChoose"
            class="text-sm lg:text-xs font-mon text-gray-700"
          >
            Id sea ullum harum nusquam, per no fastidii adipisci invenire. Vitae
            bonorum electram vel in, ea sed accommodare consectetuer. Propriae
            ponderum indoctum est id, vis cu etiam labores inimicus. Pri ut
            accumsan assueverit, sea iudico voluptaria eu, id dico mazim utroque
            eum. Vix case option mentitum no, oratio nonumes et eam, an accusata
            intellegat intellegebat sea. In sit quot regione, solum minimum ea
            mei. Per bonorum ancillae at, vocibus gloriatur vis te.Alia minim
            quaerendum ius ei. An dicit partiendo sit. Sed decore dictas
            appareat at, et quod torquatos complectitur has, quo illud dolore
            noster et. Te dissentias repudiandae vim, option detracto mea id.
          </p>
          <!-- Thông tin thêm -->
          <table v-if="moreInfor[1].isChoose" class="w-full">
            <tr>
              <td class="w-3/12">
                <span class="font-vida text-lg">Weight</span>
              </td>
              <td><span class="font-mon text-sm text-gray-800">1kg</span></td>
            </tr>
            <tr>
              <td><span class="font-vida text-lg">Dimensions</span></td>
              <td>
                <span class="font-mon text-sm text-gray-800"
                  >30 x 30 x 30 cm</span
                >
              </td>
            </tr>
          </table>
          <!-- Review -->
          <div v-if="moreInfor[2].isChoose">
            <p class="font-vida text-lg mb-4">1 review for Peach Coat</p>
            <!-- Đây là review -->
            <div>
              <div class="flex">
                <div class="flex items-center">
                  <img src="/img/avt.png" alt="avt" class="inline-block w-16" />
                </div>
                <div class="ml-4">
                  <div>
                    <font-awesome-icon :icon="['fas', 'star']" />
                    <font-awesome-icon :icon="['fas', 'star']" />
                    <font-awesome-icon :icon="['fas', 'star']" />
                    <font-awesome-icon :icon="['fas', 'star']" />
                    <font-awesome-icon :icon="['far', 'star']" />
                  </div>
                  <p>
                    <span class="font-mon text-sm text-gray-700 font-bold"
                      >Nora Berry - </span
                    ><span class="font-mon text-sm text-gray-700"
                      >March 30,2018</span
                    >
                  </p>
                  <span class="font-mon text-sm text-gray-700">Nice color</span>
                </div>
              </div>
            </div>
            <!-- Đây là AddReview -->
            <form class="w-full mt-3">
              <span class="font-mon text-sm text-gray-700">Add a review</span>
              <p class="font-mon text-sm text-gray-700">
                Your email address will not be published. Required fields are
                marked *
              </p>
              <p class="font-mon text-sm text-gray-700">Your rating *</p>
              <div>
                <font-awesome-icon :icon="['far', 'star']" />
                <font-awesome-icon :icon="['far', 'star']" />
                <font-awesome-icon :icon="['far', 'star']" />
                <font-awesome-icon :icon="['far', 'star']" />
                <font-awesome-icon :icon="['far', 'star']" />
              </div>
              <label for="commet" class="block font-mon text-sm text-gray-700"
                >Your review *</label
              >
              <!-- comment -->
              <textarea
                name="comment"
                idcomment
                rows="8"
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
                  <label
                    for="email"
                    class="font-mon text-sm text-gray-700 block"
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
            </form>
          </div>
        </div>
      </div>
      <!-- Related product -->
      <div class="w-full mt-8 px-2 lg:px-0">
        <p class="font-vida text-2xl md:px-4">Related products</p>
        <div id="products" class="flex mt-10 flex-wrap">
          <div
            v-for="product in relatedProducts"
            :key="product.url"
            class="w-full md:w-1/2 md:px-4 lg:w-1/4"
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
                    ><span class="font-vida text-lg">{{
                      product.name
                    }}</span></a
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
      </div>
    </div>
    <Slide
      :arrImgs="item.images"
      :selectedNumber="selectedNumber"
      :isExpand="isExpand"
      @cong="congNumber"
      @tru="truNumber"
      @expand="changeExpand"
      @hiddenDisplay="setHidden"
    />
  </div>
</template>

<script>
import Slide from '~/components/Slide.vue'
export default {
  name: 'Item',
  components: { Slide },
  data() {
    return {
      isHover: false,
      selectedNumber: -1,
      isExpand: false,
      item: {
        name: 'Peach coat',
        price: '75,0',
        sku: '002',
        category: 'clothes',
        infor:
          'Lorem ipsum dolor sit amet, vel dolor delicata tincidunt an, ei eum ludus dolore, id augue iudicabit conceptam cum. Quo te nominavi intellegebat. No eos porro scriptorem, sea et inimicus referrentur.',
        tag: ['DESIGN', 'IDEAS', 'NEW', 'PASTEL', 'TRENDY'],
        images: [
          {
            url: '/img/item/item1/1.jpg',
          },
          {
            url: '/img/item/item1/2.jpg',
          },
          {
            url: '/img/item/item1/3.jpg',
          },
          {
            url: '/img/item/item1/4.jpg',
          },
        ],
        description:
          'Id sea ullum harum nusquam, per no fastidii adipisci invenire. Vitae bonorum electram vel in, ea sed accommodare consectetuer. Propriae ponderum indoctum est id, vis cu etiam labores inimicus. Pri ut accumsan assueverit, sea iudico voluptaria eu, id dico mazim utroque eum. Vix case option mentitum no, oratio nonumes et eam, an accusata intellegat intellegebat sea. In sit quot regione, solum minimum ea mei. Per bonorum ancillae at, vocibus gloriatur vis te.Alia minim quaerendum ius ei. An dicit partiendo sit. Sed decore dictas appareat at, et quod torquatos complectitur has, quo illud dolore noster et. Te dissentias repudiandae vim, option detracto mea id.',
        addtionalInfo: {
          weight: 1,
          dimensions: {
            height: 30,
            width: 30,
            long: 30,
          },
        },
        review: {
          numberReview: 1,
        },
      },
      moreInfor: [
        {
          title: 'Description',
          isChoose: true,
          isHover: false,
        },
        {
          title: 'Additional information',
          isChoose: false,
          isHover: false,
        },
        {
          title: 'Review',
          isChoose: false,
          isHover: false,
        },
      ],
      relatedProducts: [
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
      ],
    }
  },
  methods: {
    getIndex(index) {
      for (let i = 0; i < this.moreInfor.length; i++) {
        if (i === index) {
          this.moreInfor[i].isChoose = true
          console.log('i +', this.moreInfor[i])
        } else this.moreInfor[i].isChoose = false
      }
    },

    congNumber() {
      if (this.selectedNumber >= 3) {
        this.selectedNumber = 0
      } else this.selectedNumber = this.selectedNumber + 1
      if (this.isExpand === true) this.isExpand = false
    },
    truNumber() {
      if (this.selectedNumber <= 0) {
        this.selectedNumber = 3
      } else this.selectedNumber = this.selectedNumber - 1
      if (this.isExpand === true) this.isExpand = false
    },
    changeExpand() {
      this.isExpand = !this.isExpand
    },
    setHidden() {
      this.selectedNumber = -1
    },
  },
}
</script>
<style scoped>

.height-50 {
  height: 50%;
}


.count-box-md {
  width: 66px;
}

.effect:hover{
   animation-name: shop;
  animation-duration: 1s;
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

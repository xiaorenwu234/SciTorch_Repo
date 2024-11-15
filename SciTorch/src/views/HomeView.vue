<script>
import HomeView_MainFrame from "@/frames/HomeView_MainFrame.vue";

export default {
  data() {
    return {
      windowWidth: window.innerWidth,
      HeadList: [
        {
          Name: "Product & Services",
          Link: "/Product",
        },
        {
          Name: "Subscribe",
          Link: "/Subscribe",
        },
        {
          Name: "Submit a paper",
          Link: "/Submit a paper",
        },
        {
          Name: "Browse",
          Link: "/Browse",
        },
        {
          Name: "Rankings",
          Link: "/Rankings",
        },
        {
          Name: "Contact",
          Link: "/Contact",
        },
      ],
      isMenuOpen: false,
    };
  },
  computed: {
    isDesktop() {
      return this.windowWidth > 1350; // 如果屏幕宽度大于1350px,认为是桌面端
    },
  },
  mounted() {
    window.addEventListener('resize', this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth;
    },
    OpenMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  },
  components: {
    HomeView_MainFrame,
  },
  watch: {
    isDesktop(newValue, oldValue) {
      if (newValue) {
        this.isMenuOpen = false;
      }
    },
  }
};
</script>

<template>
  <div class="w-full h-[80px] bg-white border-b-[2px] px-6 flex flex-row"
       :style="{ filter: isMenuOpen ? 'blur(3px)' : 'none' }">
    <div class="h-full flex mr-4">
      <div class="font-bold text-3xl m-auto text-[#073973] hover:cursor-pointer use_font">
        SciTorch
      </div>
    </div>
    <div class="h-full flex flex-row flex-1">
      <div class="flex-1 flex flex-row h-full">
        <div class="flex-1 h-full">
          <div class="mx-auto flex flex-row h-full" v-if="isDesktop">
            <div class="h-full flex mx-5 text-lg" v-for="(element,index) in HeadList" :key="index">
              <div class="my-auto Head_List">
                {{ element.Name }}
              </div>
            </div>
          </div>
        </div>
        <div class="h-full flex flex-row">
          <div class="mx-auto flex flex-row">
            <div class="h-full flex mx-5 hover:cursor-pointer">
              <img src="../icons/Shopping_Cart.svg" alt="shopping cart" class="m-auto">
            </div>
          </div>
          <div class="flex" v-if="isDesktop">
            <div
              class="text-black w-40 border-[2px] h-[44px] flex m-auto border-[#007398] mr-6 hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
              <div class="m-auto text-lg font-light">
                Create account
              </div>
            </div>
            <div
              class="w-24 h-[44px] flex m-auto bg-[#007398] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
              <div class="m-auto text-lg font-bold">
                Sign in
              </div>
            </div>
          </div>
          <div class="h-full flex ml-6" v-else>
            <img src="https://cdn.ssrn.com/ssrn-global-header/cbd90d50d6c5684432e5517eb47c279b.svg" alt="menu"
                 class="m-auto cursor-pointer" @click="OpenMenu">
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="w-80 h-full z-10 bg-white top-0 right-0 fixed slider shadow-2xl"
       :class="{'slider-open':isMenuOpen,'slider-closed':!isMenuOpen}">
    <div class="w-full">
      <img src="https://cdn.ssrn.com/ssrn-global-header/ae31995609ac601ba8a211c58aeb2b2f.svg" alt="close"
           class="absolute right-4 top-4 cursor-pointer close-icon" @click="OpenMenu">
    </div>
    <div class="w-[240px] font-extralight ml-4 mt-4 use_font text-sm" style="line-height: 25px">
      Make use of personalized features like alerts and saved searches
    </div>
    <div class="w-full flex my-4">
      <div class="text-[#007398] flex text-sm ">
        <div class="mx-4 hover:text-[#ff6300] Head_List">
          Create account
        </div>
        <div class="mx-4 hover:text-[#ff6300] Head_List font-bold">
          Sign in
        </div>
      </div>
    </div>
    <div class="w-full border-b h-2"></div>
    <div class="h-6"></div>
    <ul>
      <li v-for="(List,index) in HeadList" :key="index" class="my-5 relative text-base font-extralight use_font ml-4">
        <div class="flex">
          <div class="slider_head_list">
            {{ List.Name }}
          </div>
        </div>
      </li>
    </ul>
  </div>
  <div class="w-full h-full bg-[#f0f1f3]" :style="{ filter: isMenuOpen ? 'blur(3px)' : 'none' }">
    <HomeView_MainFrame/>
  </div>
</template>

<style scoped>
.Head_List {
  position: relative;
  display: inline-block;
}

.slider_head_list {
  position: relative;
}

.Head_List::after, .slider_head_list::after {
  content: '';
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #ff6300;
  transition: width 0.3s ease;
}

.Head_List:hover::after, .slider_head_list:hover::after {
  width: 100%;
}

.Head_List:hover, .slider_head_list:hover {
  color: #ff6300;
  transition: color 0.3s ease;
  cursor: pointer;
}

.slider {
  transition: all 0.3s ease;
}

.slider-open {
  transform: translateX(0);
}

.slider-closed {
  transform: translateX(100%);
}

.close-icon {
  filter: invert(100%) brightness(60%);
  transition: filter 0.3s ease;
}

.close-icon:hover {
  filter: invert(100%) brightness(30%);
}
</style>

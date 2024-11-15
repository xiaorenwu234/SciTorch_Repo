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
      ]
    };
  },
  computed: {
    isDesktop() {
      return this.windowWidth > 1500; // 如果屏幕宽度大于1500px,认为是桌面端
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
  },
  components:{
    HomeView_MainFrame,
  }
};
</script>

<template>
  <div class="w-full h-[80px] bg-white border-b-[2px] px-6 flex flex-row">
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
          <div
            class="text-black w-40 border-[2px] h-[44px] flex m-auto border-[#007398] mr-6 hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-lg font-light">
              Create account
            </div>
          </div>
          <div
            class="w-24 h-[44px] flex m-auto bg-[#007398] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-lg font-light">
              Sign in
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="w-full h-full bg-[#f0f1f3]">
    <HomeView_MainFrame/>
  </div>
</template>

<style scoped>
.Head_List {
  position: relative;
  display: inline-block;
}

.Head_List::after {
  content: '';
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #ff6300;
  transition: width 0.3s ease;
}

.Head_List:hover::after {
  width: 100%;
}

.Head_List:hover {
  color: #ff6300;
  transition: color 0.3s ease;
  cursor: pointer;
}
</style>

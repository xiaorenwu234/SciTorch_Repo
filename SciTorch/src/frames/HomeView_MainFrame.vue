<script>

export default {
  data() {
    return {
      windowWidth: window.innerWidth,
      Categories: [
        {
          Name: "History",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        },
        {
          Name: "Engineering",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        },
        {
          Name: "Computer Science",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        }, {
          Name: "History",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        },
        {
          Name: "Engineering",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        },
        {
          Name: "Computer Science",
          Followers: "10.4 M",
          Papers: "816 K",
          Authors: "351 K",
          SubCategory: [
            {
              Name: "Medieval History",
              Papers: "92.5 K",
            },
            {
              Name: "Ancient History",
              Papers: "87.7 K",
            },
            {
              Name: "Cultural History",
              Papers: "60 K",
            },
            {
              Name: "Early Modern History",
              Papers: "49.1 K",
            },
            {
              Name: "Urban History",
              Papers: "25.7 K",
            },
            {
              Name: "Roman History",
              Papers: "35.2 K",
            },
            {
              Name: "Ancient Greek History",
              Papers: "26.7 K",
            },
            {
              Name: "Military History",
              Papers: "34.6 K",
            },
          ]
        }
      ],
      webInfo: {
        totalPDFNumber: "55 million",
        registeredUser: "270m+",
        uploadedPapers: "55m+",
        dailyRecommendations: "20m",
      },
      showingMoreField: false,
      showLimit: 3,
    };
  },
  computed: {
    windowType() {
      if (this.windowWidth > 1200) {
        return "Desktop";
      } else if (this.windowWidth > 740) {
        return "Pad";
      } else {
        return "Phone";
      }
    },
    visibleCategories() {
      return this.showingMoreField ? this.Categories : this.Categories.slice(0, this.showLimit);
    }
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
    showMoreFields() {
      this.showingMoreField = !this.showingMoreField;
    }
  },
};

</script>

<template>
  <div class="w-full h-full home_background" v-if="windowType==='Desktop'">
    <div class="w-full flex">
      <div class="flex flex-row w-[90%] mx-auto h-[500px] pl-10">
        <div class="w-[300px] h-full mr-6">
          <div class="w-full h-full relative">
            <div class="big_text use_font m-auto top-20 cursor-default">
              Download {{ webInfo.totalPDFNumber }} PDFs for free
            </div>
          </div>
        </div>
        <div class="w-[400px] h-56 rounded-md mt-10 flex px-6 gold_background">
          <div class="my-auto w-full">
            <div class="flex flex-row w-full my-5">
              <img src="../icons/User_Blue_Icon.svg" alt="蓝色用户" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Registered Users
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                {{ webInfo.registeredUser }}
              </div>
            </div>
            <div class="flex flex-row w-full my-5">
              <img src="../icons/Paper_Gold_Icon.svg" alt="金色论文" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Uploaded Papers
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                {{ webInfo.uploadedPapers }}
              </div>
            </div>
            <div class="flex flex-row w-full my-5">
              <img src="../icons/Recommend_Icon.svg" alt="推荐" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Daily Recommendations
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                {{ webInfo.dailyRecommendations }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="w-full flex">
      <div class="w-[90%] mx-auto px-10">
        <div class="flex flex-row mt-6 mb-6 w-full mx-auto">
          <div class="text-3xl use_font">
            Explore our top research interests
          </div>
          <div class="flex-1"></div>
          <div class="text-m font-bold mr-4 text-blue-800 cursor-pointer hover:underline hover:text-blue-900">
            Browse All Topics
          </div>
        </div>
        <div class="my-6 w-full mx-auto rounded-md border h-60 flex flex-row gold_background"
             v-for="(Category,index) in visibleCategories" :key="index">
          <div class="w-[500px] pl-8 my-auto">
            <div class="text-4xl use_font cursor-pointer hover:underline ml-[-5px]">
              {{ Category.Name }}
            </div>
            <div class="text-md flex mt-6">
              <div class="mr-5">
                <div class="font-bold tracking-wide">
                  {{ Category.Followers }}
                </div>
                <div>
                  Followers
                </div>
              </div>
              <div class="mr-5">
                <div class="font-bold tracking-wide text-center">
                  {{ Category.Papers }}
                </div>
                <div>
                  Papers
                </div>
              </div>
              <div>
                <div class="font-bold tracking-wide text-center">
                  {{ Category.Authors }}
                </div>
                <div>
                  Authors
                </div>
              </div>
            </div>
          </div>
          <div class="my-auto flex flex-wrap w-full text-md">
            <div class="w-1/2 flex text-blue-800 cursor-pointer hover:text-blue-900 hover:underline my-3 px-6"
                 style="font-weight: 600"
                 v-for="(Sub,SubIndex) in Category.SubCategory" :key="SubIndex">
              <div>
                {{ Sub.Name }}
              </div>
              <div class="flex-1">

              </div>
              <div>
                {{ Sub.Papers }} Papers
              </div>
            </div>
          </div>
        </div>
        <div class="w-full flex mt-6">
          <div @click="showMoreFields"
               class="w-48 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-xl font-medium">
              {{ showingMoreField ? "Show Less" : "Show More" }}
            </div>
          </div>
        </div>
        <div class="w-full text-4xl use_font text-center mb-12 mt-16 ">
          Join 276 million academics and researchers
        </div>
        <div class="w-full flex">
          <div class="mx-auto flex flex-row">
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/track-impact.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Track your impact
              </div>
              <div class="w-full px-5 text-center">
                Share your work with other academics, grow your audience and track your impact on your field with our
                robust analytics
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Track your impact
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/discover-research.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Discover new research
              </div>
              <div class="w-full px-5 text-center">
                Get access to millions of research papers and stay informed with the important topics around the world
              </div>
              <div class="w-full justify-center flex">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline mb-32">
                    Discover new research
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/publish-work.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Publish your work
              </div>
              <div class="w-full px-5 text-center">
                Publish your research with fast and rigorous service through Academia.edu Journals. Get instant
                worldwide
                dissemination of your work
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Publish your work
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-16 w-full text-center text-4xl use_font">
          Unlock your imagination with SciTorch !
        </div>
        <div class="w-full flex mt-6">
          <div
              class="w-52 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-xl font-normal">
              Sign in
            </div>
          </div>
        </div>
        <div class="w-full flex mt-16">
          <div class="mx-auto flex flex-row text-white">
            <div class="flex flex-col">
              <div class="h-1/5 flex">
                <div class="m-auto text-4xl use_font text-black text-center">
                  <div>Real stories from</div>
                  <div>real people</div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mx-3 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="https://a.academia-assets.com/images/landing/t-alisdair.png" alt="Alisdair"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Alisdair
                </div>
                <div class="text-center">
                  University of Highlands
                </div>
                <div class="text-center">
                  and Islands
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “I go through all the articles in the bulk download, save the ones that are clearly going to be
                    useful
                    and
                    discard the remainder. This saves loads of time but also points me in directions I might not
                    otherwise
                    have thought of looking.”
                  </div>
                </div>
              </div>
            </div>
            <div class="flex flex-col mx-12">
              <div class="flex flex-col">
                <div class="w-[360px] h-auto pb-8 bg-[#2B3654] rounded-xl">
                  <div class="text-center text-sm mb-4 mt-6">
                    RESEARCHER
                  </div>
                  <img src="/Trevor_Image.png" alt="Trevor"
                       class="h-32 mx-auto">
                  <div class="text-center font-bold mt-5 mb-2">
                    Trevor
                  </div>
                  <div class="text-center">
                    University of Sydney
                  </div>
                  <div class="w-full flex my-5">
                    <div class="m-auto border-b border-white w-12"></div>
                  </div>
                  <div class="w-full flex">
                    <div class=" text-xl w-full px-6">
                      “The bulk downloads give me the chance to read more related articles as well as seeing what
                      research
                      is citing the article I am looking at. It also helps me rapidly expand my personal digital library
                      of
                      references.”
                    </div>
                  </div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mt-6 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="/Paul_Image.png" alt="Paul"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Paul
                </div>
                <div class="text-center">
                  Electrical Engineer
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “Bulk download provides me limitless opportunities to access books and research materials which I
                    cannot ordinarily access.”
                  </div>
                </div>
              </div>
            </div>
            <div class="flex flex-col mx-3">
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="https://a.academia-assets.com/images/landing/t-steve.png" alt="Alisdair"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Steve
                </div>
                <div class="text-center">
                  Clinical Psychologist
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “The value of Bulk Download is in providing a fairly comprehensive overview of almost any topic
                    within Academia.”
                  </div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mt-6 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="https://a.academia-assets.com/images/landing/t-wojtek.png" alt="Alisdair"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Wojtek
                </div>
                <div class="text-center">
                  University of Business and
                </div>
                <div class="text-center">
                  Administration in Gdynia
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “Bulk Download helps me get papers from younger scholars. It also surfaces teaching texts that
                    assist in the development of my own hand-out materials for my students.”
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="text-5xl text-center w-full use_font mt-16">
          Contains Papers from over 15,000 universities
        </div>
        <div class="w-full mb-10">
          <div class="flex my-16">
            <img src="../icons/Oxford_Logo.svg" alt="牛津大学" class="h-[52px] mx-auto">
            <img src="../icons/UCB_Logo.svg" alt="伯克利大学" class="h-[52px] mx-auto">
            <img src="../icons/Mexico_Logo.svg" alt="墨西哥大学" class="h-[52px] mx-auto">
          </div>
          <div class="w-full flex">
            <div class="w-4/5 min-w-[1200px] flex h-[315px] mx-auto" style="background: #f9f7f4;">
              <img class="h-full aspect-auto" src="/Church_Image.png" alt="教堂">
              <div class="flex m-auto flex-wrap">
                <div class="text-4xl font-normal use_font px-16 w-full text-center" style="line-height:44px">
                  Get started and find the best quality research in SciTorch
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="w-full h-full home_background" v-if="windowType==='Pad'">
    <div class="w-full flex">
      <div class="flex flex-row w-[90%] mx-auto h-[500px] pl-10">
        <div class="w-[300px] h-full mr-6">
          <div class="w-full h-full relative">
            <div class="big_text use_font m-auto top-20">
              Download 55 million PDFs for free
            </div>
          </div>
        </div>
        <div class="w-[400px] h-56 rounded-md mt-10 flex px-6 gold_background">
          <div class="my-auto w-full">
            <div class="flex flex-row w-full my-5">
              <img src="../icons/User_Blue_Icon.svg" alt="蓝色用户" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Registered Users
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                270m+
              </div>
            </div>
            <div class="flex flex-row w-full my-5">
              <img src="../icons/Paper_Gold_Icon.svg" alt="金色论文" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Uploaded Papers
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                55m+
              </div>
            </div>
            <div class="flex flex-row w-full my-5">
              <img src="../icons/Recommend_Icon.svg" alt="推荐" class="h-10 mr-6">
              <div class="text-black text-xl my-auto">
                Daily Recommendations
              </div>
              <div class="flex-1"></div>
              <div class="text-black text-xl font-bold my-auto">
                20m
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="w-full flex">
      <div class="w-full mx-auto px-3">
        <div class="flex flex-row mt-6 mb-6 w-full mx-auto px-8">
          <div class="text-3xl use_font">
            Explore our top research interests
          </div>
          <div class="flex-1"></div>
          <div class="text-m mr-4 font-bold text-blue-800 cursor-pointer hover:underline hover:text-blue-900">
            Browse All Topics
          </div>
        </div>
        <div class="my-6 w-full mx-auto rounded-md border flex flex-row gold_background"
             v-for="(Category,index) in Categories" :key="index">
          <div class="w-[500px] pl-8 my-auto">
            <div class="text-4xl use_font cursor-pointer hover:underline ml-[-5px]">
              {{ Category.Name }}
            </div>
            <div class="text-md flex mt-6">
              <div class="mr-5">
                <div class="font-bold tracking-wide">
                  {{ Category.Followers }}
                </div>
                <div>
                  Followers
                </div>
              </div>
              <div class="mr-5">
                <div class="font-bold tracking-wide text-center">
                  {{ Category.Papers }}
                </div>
                <div>
                  Papers
                </div>
              </div>
              <div>
                <div class="font-bold tracking-wide text-center">
                  {{ Category.Authors }}
                </div>
                <div>
                  Authors
                </div>
              </div>
            </div>
          </div>
          <div class="my-auto flex flex-wrap w-full text-md">
            <div class="w-full flex text-blue-800 hover:text-blue-900 cursor-pointer hover:underline my-3 px-6"
                 style="font-weight: 600"
                 v-for="(Sub,SubIndex) in Category.SubCategory" :key="SubIndex">
              <div>
                {{ Sub.Name }}
              </div>
              <div class="flex-1"></div>
              <div>
                {{ Sub.Papers }} Papers
              </div>
            </div>
          </div>
        </div>
        <div class="w-full flex mt-6">
          <div
              class="w-48 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-xl font-medium">
              {{ showingMoreField ? "Show Less" : "Show More" }}
            </div>
          </div>
        </div>
        <div class="w-full text-4xl use_font text-center mb-6 mt-16">
          Join 276 million academics and researchers
        </div>
        <div class="w-full flex">
          <div class="mx-auto flex flex-row">
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/track-impact.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Track your impact
              </div>
              <div class="w-full px-5 text-center">
                Share your work with other academics, grow your audience and track your impact on your field with our
                robust analytics
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Track your impact
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/discover-research.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Discover new research
              </div>
              <div class="w-full px-5 text-center">
                Get access to millions of research papers and stay informed with the important topics around the world
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Discover new research
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/publish-work.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Publish your work
              </div>
              <div class="w-full px-5 text-center">
                Publish your research with fast and rigorous service through Academia.edu Journals. Get instant
                worldwide
                dissemination of your work
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Publish your work
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-16 w-full text-center text-4xl use_font">
          Unlock your imagination with SciTorch !
        </div>
        <div class="w-full flex mt-6">
          <div
              class="w-52 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-lg font-light">
              Sign in
            </div>
          </div>
        </div>
        <div class="w-full flex mt-16">
          <div class="mx-auto flex flex-row text-white">
            <div class="flex flex-col">
              <div class="h-1/3 flex">
                <div class="m-auto text-4xl use_font text-black text-center">
                  <div>Real stories from</div>
                  <div>real people</div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mx-3 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="https://a.academia-assets.com/images/landing/t-alisdair.png" alt="Alisdair"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Alisdair
                </div>
                <div class="text-center">
                  University of Highlands
                </div>
                <div class="text-center">
                  and Islands
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “I go through all the articles in the bulk download, save the ones that are clearly going to be
                    useful
                    and
                    discard the remainder. This saves loads of time but also points me in directions I might not
                    otherwise
                    have thought of looking.”
                  </div>
                </div>
              </div>
            </div>
            <div class="flex flex-col mx-12">
              <div class="flex flex-col">
                <div class="w-[360px] h-auto pb-8 bg-[#2B3654] rounded-xl">
                  <div class="text-center text-sm mb-4 mt-6">
                    RESEARCHER
                  </div>
                  <img src="/Trevor_Image.png" alt="Trevor"
                       class="h-32 mx-auto">
                  <div class="text-center font-bold mt-5 mb-2">
                    Trevor
                  </div>
                  <div class="text-center">
                    University of Sydney
                  </div>
                  <div class="w-full flex my-5">
                    <div class="m-auto border-b border-white w-12"></div>
                  </div>
                  <div class="w-full flex">
                    <div class=" text-xl w-full px-6">
                      “The bulk downloads give me the chance to read more related articles as well as seeing what
                      research
                      is citing the article I am looking at. It also helps me rapidly expand my personal digital library
                      of
                      references.”
                    </div>
                  </div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mt-6 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="/Paul_Image.png" alt="Paul"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Paul
                </div>
                <div class="text-center">
                  Electrical Engineer
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “Bulk download provides me limitless opportunities to access books and research materials which I
                    cannot ordinarily access.”
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="text-5xl text-center w-full use_font mt-16">
          Contains Papers from over 15,000 universities
        </div>
        <div class="w-full mb-10">
          <div class="flex my-16">
            <img src="../icons/Oxford_Logo.svg" alt="牛津大学" class="h-[52px] mx-auto">
            <img src="../icons/UCB_Logo.svg" alt="伯克利大学" class="h-[52px] mx-auto">
            <img src="../icons/Mexico_Logo.svg" alt="墨西哥大学" class="h-[52px] mx-auto">
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="w-full h-full home_background" v-if="windowType==='Phone'">
    <div class="w-full flex">
      <div class="w-full flex opacity_background">
        <div class="flex flex-col w-[90%] mx-auto h-[500px] pl-10 mb-8">
          <div class="w-full h-full mr-6">
            <div class="w-full h-full relative">
              <div class="big_text use_font m-auto top-20 text-center">
                Download 55 million PDFs for free
              </div>
            </div>
          </div>
          <div class="w-full h-56 rounded-md mt-10 flex px-6 gold_background">
            <div class="my-auto w-full">
              <div class="flex flex-row w-full my-5">
                <img src="../icons/User_Blue_Icon.svg" alt="蓝色用户" class="h-10 mr-6">
                <div class="text-black text-xl my-auto">
                  Registered Users
                </div>
                <div class="flex-1"></div>
                <div class="text-black text-xl font-bold my-auto">
                  270m+
                </div>
              </div>
              <div class="flex flex-row w-full my-5">
                <img src="../icons/Paper_Gold_Icon.svg" alt="金色论文" class="h-10 mr-6">
                <div class="text-black text-xl my-auto">
                  Uploaded Papers
                </div>
                <div class="flex-1"></div>
                <div class="text-black text-xl font-bold my-auto">
                  55m+
                </div>
              </div>
              <div class="flex flex-row w-full my-5">
                <img src="../icons/Recommend_Icon.svg" alt="推荐" class="h-10 mr-6">
                <div class="text-black text-xl my-auto">
                  Daily Recommendations
                </div>
                <div class="flex-1"></div>
                <div class="text-black text-xl font-bold my-auto">
                  20m
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="w-full flex">
      <div class="w-full mx-auto px-3">
        <div class="flex flex-row mt-6 mb-6 w-full mx-auto px-8">
          <div class="text-3xl use_font">
            Explore our top research interests
          </div>
          <div class="flex-1"></div>
          <div class="text-m mr-4 font-bold text-blue-800 cursor-pointer hover:underline hover:text-blue-900">
            Browse All Topics
          </div>
        </div>
        <div class="my-6 w-full mx-auto rounded-md border flex flex-col gold_background"
             v-for="(Category,index) in Categories" :key="index">
          <div class="my-auto w-full">
            <div class="text-4xl use_font cursor-pointer hover:underline text-center w-full ml-[-5px]">
              {{ Category.Name }}
            </div>
            <div class="flex w-full">
              <div class="text-md flex mt-6 mx-auto">
                <div class="mr-5">
                  <div class="font-bold tracking-wide text-center">
                    {{ Category.Followers }}
                  </div>
                  <div>
                    Followers
                  </div>
                </div>
                <div class="mr-5">
                  <div class="font-bold tracking-wide text-center text-center">
                    {{ Category.Papers }}
                  </div>
                  <div>
                    Papers
                  </div>
                </div>
                <div>
                  <div class="font-bold tracking-wide text-center text-center">
                    {{ Category.Authors }}
                  </div>
                  <div>
                    Authors
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="my-auto flex flex-wrap w-full text-md">
            <div class="w-full flex text-blue-800 hover:text-blue-900 cursor-pointer hover:underline my-3 px-6"
                 style="font-weight: 600"
                 v-for="(Sub,SubIndex) in Category.SubCategory" :key="SubIndex">
              <div>
                {{ Sub.Name }}
              </div>
              <div class="flex-1"></div>
              <div>
                {{ Sub.Papers }} Papers
              </div>
            </div>
          </div>
        </div>
        <div class="w-full flex mt-6">
          <div
              class="w-48 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-xl font-medium">
              {{ showingMoreField ? "Show Less" : "Show More" }}
            </div>
          </div>
        </div>
        <div class="w-full text-4xl use_font text-center mb-6 mt-16">
          Join 276 million academics and researchers
        </div>
        <div class="w-full flex">
          <div class="mx-auto flex flex-row">
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/track-impact.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Track your impact
              </div>
              <div class="w-full px-5 text-center">
                Share your work with other academics, grow your audience and track your impact on your field with our
                robust analytics
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Track your impact
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/discover-research.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Discover new research
              </div>
              <div class="w-full px-5 text-center">
                Get access to millions of research papers and stay informed with the important topics around the world
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Discover new research
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
            <div class="mx-2 h-auto pb-6 bg-[#2B3654] min-w-72 w-1/3 w-1/3 rounded-xl text-white">
              <div class="w-full h-[45%] flex">
                <img src="https://a.academia-assets.com/images/landing/publish-work.svg" alt="fluctuate"
                     class="h-20 m-auto">
              </div>
              <div class="w-full text-center font-semibold mb-3" style="font-size: 33px;line-height: 37px;">
                Publish your work
              </div>
              <div class="w-full px-5 text-center">
                Publish your research with fast and rigorous service through Academia.edu Journals. Get instant
                worldwide
                dissemination of your work
              </div>
              <div class="w-full justify-center flex">
                <div class="mb-32">
                  <div class="mx-auto flex mt-6 cursor-pointer hover:underline">
                    Publish your work
                    <img src="https://a.academia-assets.com/images/landing/icon-right-arrow.svg" alt="arrow"
                         class="ml-1">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-16 w-full text-center text-4xl use_font">
          Unlock your imagination with SciTorch !
        </div>
        <div class="w-full flex mt-6">
          <div
              class="w-52 h-[44px] flex m-auto bg-[#0645B1] text-white hover:bg-[#ff6300] hover:text-white transition-all duration-300 hover:border-none hover:cursor-pointer">
            <div class="m-auto text-lg font-light">
              Sign in
            </div>
          </div>
        </div>
        <div class="w-full flex mt-16">
          <div class="mx-auto flex flex-row text-white">
            <div class="flex flex-col mx-10">
              <div class="flex flex-col">
                <div class="w-[360px] h-auto pb-8 bg-[#2B3654] rounded-xl">
                  <div class="text-center text-sm mb-4 mt-6">
                    RESEARCHER
                  </div>
                  <img src="/Trevor_Image.png" alt="Trevor"
                       class="h-32 mx-auto">
                  <div class="text-center font-bold mt-5 mb-2">
                    Trevor
                  </div>
                  <div class="text-center">
                    University of Sydney
                  </div>
                  <div class="w-full flex my-5">
                    <div class="m-auto border-b border-white w-12"></div>
                  </div>
                  <div class="w-full flex">
                    <div class=" text-xl w-full px-6">
                      “The bulk downloads give me the chance to read more related articles as well as seeing what
                      research
                      is citing the article I am looking at. It also helps me rapidly expand my personal digital library
                      of
                      references.”
                    </div>
                  </div>
                </div>
              </div>
              <div class="w-[360px] h-auto pb-8 bg-[#2B3654] mt-6 rounded-xl">
                <div class="text-center text-sm mb-4 mt-8">
                  RESEARCHER
                </div>
                <img src="/Paul_Image.png" alt="Paul"
                     class="h-32 mx-auto">
                <div class="text-center font-bold mt-5 mb-2">
                  Paul
                </div>
                <div class="text-center">
                  Electrical Engineer
                </div>
                <div class="w-full flex my-5">
                  <div class="m-auto border-b border-white w-12"></div>
                </div>
                <div class="w-full flex">
                  <div class=" text-xl w-full px-6">
                    “Bulk download provides me limitless opportunities to access books and research materials which I
                    cannot ordinarily access.”
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="text-5xl text-center w-full use_font mt-16">
          Contains Papers from over 15,000 universities
        </div>
        <div class="w-full mb-10">
          <div class="flex my-16">
            <img src="../icons/Oxford_Logo.svg" alt="牛津大学" class="h-[52px] mx-auto">
            <img src="../icons/UCB_Logo.svg" alt="伯克利大学" class="h-[52px] mx-auto">
            <img src="../icons/Mexico_Logo.svg" alt="墨西哥大学" class="h-[52px] mx-auto">
          </div>
        </div>
        <!--        <div class="w-full flex">-->
        <!--          <div class="w-4/5 min-w-[1200px] flex h-[315px] mx-auto" style="background: #f9f7f4;">-->
        <!--            <img class="h-full aspect-auto" src="/Church_Image.png" alt="教堂">-->
        <!--            <div class="flex m-auto flex-wrap">-->
        <!--              <div class="text-4xl font-bold use_font px-16 w-full text-center" style="line-height:44px">-->
        <!--                Get started and find the best quality research in SciTorch-->
        <!--              </div>-->
        <!--            </div>-->
        <!--          </div>-->
        <!--        </div>-->
      </div>
    </div>
  </div>
</template>

<style scoped>
.big_text {
  font-size: 38px;
  line-height: 60px;
  font-weight: normal;
}

.top-20 {
  position: absolute;
  top: 40px;
}

.home_background {
  background: #fff url('/HomeView_Background.png') no-repeat;
  background-position-x: 45vw;
  background-size: 800px;
}

.gold_background {
  background: #f9f7f4;
  border: 1px solid #e0d9c6;
}

.opacity_background {
  position: relative;
  background: linear-gradient(rgba(255, 255, 255, 0.5), rgba(255, 255, 255, 0.5)),
  url('/HomeView_Background.png');
  background-size: cover;
  background-position: center;
}
</style>

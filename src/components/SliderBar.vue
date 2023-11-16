<script setup>
import { ref, watchEffect } from 'vue';
const props = defineProps({
    isMobile: Boolean
});
const isMobile = ref(props.isMobile);
const openDrawer = ref(false);
const slecetDrawer = ref(0)
const selectSlider = (idx) => {
    slecetDrawer.value = idx === slecetDrawer.value ? null : idx;
};
const selcetList = ['白頭翁的特性', '白頭翁的故事', '白頭翁的美照', '白頭翁的危機']

watchEffect(() => {
  if (props.isMobile !== isMobile.value) {
    isMobile.value = props.isMobile;
  }
});
</script>
<template>
    <div v-if="!isMobile" class="bg-white md:w-[440px] xl:w-[345px] py-12">
    <div class="flex relative">
        <h1 class="text-[30px] font-bold text-black text-center my-12 w-full tracking-tighter pt-6 xl:md:pt-0">白頭翁不吃小米</h1>
        <div class="circle absolute border rounded-full right-16 -top-12 xl:-right-12 xl:top-2">
            <div class="line relative top-6 left-6"></div>
            <div class="circle2 absolute top-[2.6rem] right-9"></div>
            <div class="line2 relative -top-[3.2rem] left-6"></div>
            <div class="line3 absolute top-[2.4rem] right-3"></div>
        </div>
    </div>
        <div class="text-[18px] font-bold text-center m-auto mt-12" >
            <div @click="selectSlider(idx)" class="my-5  cursor-pointer hover:text-[#AA6666] hover:underline hover:underline-offset-2 hover:decoration-2"  v-for="(item, idx) in selcetList" :key="idx"
                :class="{'text-[#AA6666] underline underline-offset-2 decoration-2':slecetDrawer === idx, 'text-black': slecetDrawer !== idx}">
              {{item}}
            </div>
        </div>
    </div>
    <div v-else class="bg-white h-[90px] w-full flex items-center px-6" :class="{'border-b-4 border-black drop-shadow-xl': !openDrawer}" style="box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.5);"> 
        <div class="w-1/4" @click="openDrawer = !openDrawer">
            <img src="../assets/hamburgur icon.svg" alt="">
        </div>
        <div class="text-[20px] font-bold w-2/4">白頭翁不吃小米</div>
        <div class="text-[20px] font-bold w-1/4 flex justify-center">
            <div class="circle2 relative border rounded-full ">
            <div class="line relative top-2 left-[0.6rem]"></div>
            <div class="circle3 absolute top-[1.3rem] right-5"></div>
            <div class="line2 relative -top-[5.2rem] left-[0.6rem]"></div>
            <div class="line3  absolute top-[1.1rem] right-[0.2rem]"></div>
        </div>
        </div>
    </div>
    <div class="h-[190px] bg-white" v-if="openDrawer" :class="{'border-b-4 border-black drop-shadow-xl': openDrawer}" style="box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.5);">
        <div class="text-[18px] font-bold text-center m-auto py-6">
          <div @click="selectSlider(idx)" class="my-3 cursor-pointer hover:text-[#AA6666] hover:underline hover:underline-offset-2 hover:decoration-2"  v-for="(item, idx) in selcetList" :key="idx"
                :class="{'text-[#AA6666] underline underline-offset-2 decoration-2':slecetDrawer === idx, 'text-black': slecetDrawer !== idx}">
              {{item}}
            </div>
        </div>
    </div>
</template>

<style style="scss">
.circle {
  width: 100px;
  height: 100px;
  background-color: white;
  border-radius: 50%;
  box-shadow: 1px 2px 2px 2px rgba(0, 0, 0, 0.5);

}
.circle .line {
  width: 50px;
  height: 95px;
  border-radius: 170px 50px 0 0 / 120px 55px 0 0;
  border-top: 10px solid black;
  border-left-width: 12px;
  border-right-width: 12px;
  transform:  rotate(0deg);
  }
  .circle .circle2{
  width: 10px;
  height: 10px;
  border-radius: 100%;
  background-color: black;
  }
  .circle .line2 {
  width: 50px;
  height: 30px;
  border-radius: 180px 40px 0 0 / 100px 0px 0 0;
  border-top: 12px solid black;
  transform:  rotate(182deg);
  }
.circle .line3 {
  width: 15px;
  height: 10px;
  border-radius: 0px 20px 0 0 / 15px 10px 0 0;
  border-top: 8px solid black;
  transform:  rotate(-5deg);
}
.circle2 {
  width: 50px;
  height: 50px;
  background-color: white;
  border-radius: 50%;
  box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.25);
}
.circle2 .line {
  width: 28px;
  height: 95px;
  border-radius: 120px 40px 0 0 / 80px 60px 0 0;
  border-top: 6px solid black;
  border-left-width: 12px;
  border-right-width: 12px;
  transform:  rotate(0deg);
  }
  .circle2 .circle3{
  width: 5px;
  height: 5px;
  border-radius: 100%;
  background-color: black;
  }
  .circle2 .line2 {
  width: 28px;
  height: 30px;
  border-radius: 80px 20px 0 0 / 60px 20px 0 0;
  border-top: 8px solid black;
  transform:  rotate(182deg);
  }
.circle2 .line3 {
  width: 10px;
  height: 10px;
  border-radius: 0px 20px 0 0 / 15px 10px 0 0;
  border-top: 6px solid black;
  transform:  rotate(-14deg);
}
</style>
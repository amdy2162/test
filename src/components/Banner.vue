
<script setup>
import {ref, watchEffect} from 'vue';
const props = defineProps({
    isMobile: Boolean
});
const isMobile = ref(props.isMobile);

watchEffect(() => {
  if (props.isMobile !== isMobile.value) {
    isMobile.value = props.isMobile;
  }
});
</script>
<template>
   <div v-if="!isMobile" class="bg-white w-[1095px] overflow-hidden">
    <div class="h-[634px] bg text-white flex justify-end items-end" >
      <div class="mx-[3.1em]">
        <h1 class="text-[48px] font-bold text-end mb-4">白頭翁 (Chinese bulbul)</h1>
      <h2 class="text-[18px] text-end mb-10">又名白頭鵯。以果實、昆蟲為主食，無法消化小米、穀類。平均壽命約 8~10 年。</h2>
      </div>
    </div>
    <div class="bg-[#dcccbc] text-black font-bold xl:h-[367px] w-full grid grid-cols-3 gap-5 xl:px-12 px-3">
      <div class="block xl:flex py-12 xl:px-4 relative">
        <div class="text-[36px] vertical-rl w-full xl:w-20 xl:px-3 text-center xl:text-start mb-3 xl:mb-0">外觀</div>
        <div class="decorate absolute top-[4.3rem] left-28 xl:top-[6.8rem] xl:left-[3.3rem] h-[1.6rem] w-[1.8rem]"></div>
        <div class="text-[16px] leading-5 xl:w-52">白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。
          耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。
        </div>
      </div>
      <div class="block xl:flex py-12 xl:px-4 relative">
        <div class="text-[36px] vertical-rl w-full xl:w-20 xl:px-3 text-center xl:text-start mb-3 xl:mb-0">棲地</div>
        <div class="decorate absolute top-[4.3rem] left-28 xl:top-[6.8rem] xl:left-[3.3rem] h-[1.6rem] w-[1.8rem]"></div>
        <div class=" text-[16px] leading-5 xl:w-52">白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，
          以及校園、公園、庭院、行道中的各種高高的電線與樹上。
        </div>
      </div>
      <div class="block xl:flex py-12 xl:px-4 relative">
        <div class="text-[36px] vertical-rl w-full xl:w-20 xl:px-3 text-center xl:text-start mb-3 xl:mb-0">食性</div>
        <div class="decorate absolute top-[4.3rem] left-28 xl:top-[6.8rem] xl:left-[3.3rem] h-[1.6rem] w-[1.8rem]"></div>
        <div class="text-[16px] leading-5 xl:w-52">以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。</div>
      </div>
    </div>
    </div>
    <div v-else class="w-full">
      <div class="h-[312px] bg2 text-white overflow-hidden" >
        <div class="grid grid-cols-2 text-end w-11/12 my-24">
        <h1 class=" col-start-2 text-[48px] font-bold mb-4 w-52 ">
          <div class="">白頭翁 </div>
          <div class="">(Chinese</div>
        <div class="">bulbul)</div></h1>
      <h2 class=" col-span-2 text-[18px] w-full">
        <div class="mb-1">又名白頭鵯。以果實、昆蟲為主食，無法</div>
        <div class="">消化小米、穀類。平均壽命約 8~10 年。</div>
      </h2>
      </div>
      </div>
      <div class="bg-[#dcccbc] text-black font-bold ">
      <div class="flex px-8 py-10 relative">
        <div class="text-[36px]  vertical-rl px-5 ">外觀</div>
        <div class="decorate absolute top-[6rem] left-20 h-[1.6rem] w-[1.8rem]"></div>
        <div class="px-4  text-[16px]  leading-5">白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。
          耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。
        </div>
      </div>
      <div class="flex px-8 py-10 relative">
        <div class="text-[36px] vertical-rl px-5">棲地</div>
        <div class="decorate absolute top-[6rem] left-20 h-[1.6rem] w-[1.8rem]"></div>
        <div class="px-4 text-[16px] leading-5">白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，
          以及校園、公園、庭院、行道中的各種高高的電線與樹上。
        </div>
      </div>
      <div class="flex px-8 py-10 relative">
        <div class="text-[36px] vertical-rl px-5">食性</div>
        <div class="decorate absolute top-[6rem] left-20 h-[1.6rem] w-[1.8rem]"></div>
        <div class="text-[16px] px-4 leading-5">以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。</div>
      </div>
    </div>
    </div>
</template>
  
<style>
  .bg{
    background: url('../assets/banner.png');
    background-repeat: no-repeat;
    background-position: left 66% top 48.5%;
    background-size: 188% 184%;
    width: 100%;
  }
  .bg2{
    background: url('../assets/banner.png');
    background-repeat: no-repeat;
    background-position: left 66% top 50.5%;
    background-size: 220% 180%;
    width: 100%;
  }
  .decorate {
    background: url('../assets/decorate.svg');
    background-repeat: no-repeat;
  }
</style>
  
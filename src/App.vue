<script setup>
import SliderBar from './components/SliderBar.vue';
import Banner from './components/Banner.vue';
import { ref, onMounted, onUnmounted } from 'vue';

const isMobile = ref(window.innerWidth < 768);

onMounted(() => {
    window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
    window.removeEventListener('resize', handleResize);
});

function handleResize() {
    isMobile.value = window.innerWidth < 768;
}

</script>

<template>
        <div class="w-full h-full" :class="{'flex':!isMobile, 'block': isMobile}">
                <SliderBar :isMobile="isMobile" />
                <Banner :isMobile="isMobile"/>
        </div>
</template>

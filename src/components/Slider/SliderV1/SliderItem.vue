<script setup lang="ts">
import { ref, defineProps, computed, toRefs, watch } from 'vue'
import { MainBanner } from '../../../typings/MainBanner'

interface Prop {
    data: MainBanner;
    currentSlide: number;
    index: number;
    direction: string;
}

const props = defineProps<Prop>();

const { direction, data } = toRefs(props);

const input = ref<any>(null)

const transitionEffect = computed(() => {
    return direction.value === 'right' ? 'slide-out' : 'slide-in'
})
</script>


<template>
    <transition :name="transitionEffect">
        <div
            class="absolute top-0 bottom-0 left-0 right-0"
            v-show="currentSlide === index"
        >
            <div class="relative flex items-center justify-center w-full h-full">
                <img 
                    :src="data.imageSourceUrl"
                    :alt="`slide-${index}`"
                    class="block h-full"
                />
            </div>
            <!-- <div class="absolute left-0 flex flex-col justify-center h-full max-w-[60%] pl-[12%]">
                <h2 class="md:text-5xl xl:text-6xl text-white font-din-next-lt-pro-light" v-html="dataTitle" ></h2>
                <h2 class="mt-5 text-sm md:text-2xl xl:text-3xl text-white font-din-next-lt-pro-light">{{ data.subTitle }}</h2>
            </div>
            <div class="relative flex items-end justify-end h-full">
                <img
                    :src="data.imageSourceUrl"
                    :alt="`slide-${index}`"
                    class="block h-full"
                />
            </div> -->
        </div>
    </transition>
</template>

<style scoped>
.slide-in-enter-active,
.slide-in-leave-active,
.slide-out-enter-active,
.slide-out-leave-active {
    transition: all 1s ease-in-out;
}
.slide-in-enter-from {
    transform: translateX(-100%);
}
.slide-in-leave-to {
    transform: translateX(100%);
}
.slide-out-enter-from {
    transform: translateX(100%);
}
.slide-out-leave-to {
    transform: translateX(-100%);
}
</style>

<script setup lang="ts">

</script>

<template>
    <div class="bg-no-repeat bg-cover wrapper h-[720px] lg:h-[480px] xl:h-[540px] 2xl:h-[720px]">
        <div
            class="flex flex-col items-end justify-between h-full p-10 md:p-20 md:flex-row wrapper__inner"
        >
            <div class="text-center md:text-left mt-96">
                <h4 class="text-4xl xl:text-5xl 2xl:text-6xl text-hydrate font-questrial">How to find our products</h4>
                <p
                    class="text-base xl:text-lg 2xl:text-2xl mt-5 xl:mt-8 font-medium text-gray-400 font-questrial"
                >Our products are exclusively available through our partner clinics and dermatologies.</p>
                <p
                    class="text-base xl:text-lg 2xl:text-2xl font-medium text-gray-400 font-questrial"
                >Please make sure to consult with our physician to get the best experience with our product.</p>
            </div>
            <div class="flex items-center w-full md:w-fit">
                <a
                    href="/clinics"
                    @click="$router.push('/clinics')"
                    class="w-full py-5 px-20 text-lg text-center border px-auto md:w-fit xl:px-24 xl:text-3xl border-hydrate text-hydrate hover:bg-hydrate hover:text-white font-questrial"
                >Find Us</a>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.wrapper {
    background-image: url("/img/medical-building-interior.jpeg");
    background-position: center 70%;
    &__inner {
        background: linear-gradient(
            0deg,
            rgba(255, 255, 255, 1) 0%,
            rgba(255, 255, 255, 1) 35%,
            rgba(255, 255, 255, 0) 100%
        );
    }
}

@media (min-width: 768px) {
    .wrapper {
        background-image: url("/img/medical-building-interior.jpeg");
        background-position: center 70%;

        &__inner {
            background: linear-gradient(
                0deg,
                rgba(255, 255, 255, 1) 0%,
                rgba(255, 255, 255, 1) 15%,
                rgba(255, 255, 255, 0) 100%
            );
        }
    }
}
</style>
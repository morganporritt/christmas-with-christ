<template>
  <div>
    <div class="relative">
      <div
        class="page_banner_image w-full bg-center bg-cover"
        :style="{
          backgroundImage:
            'url(' + require('@/assets/images/background.png') + ')',
        }"
        style="height: calc(100vh - 3rem)"
      >
        <div
          class="absolute pr-3 text-center text-gray-50 top-24 left-0.5 md:left-4 w-max"
        >
          <h1 class="text-xl sm:text-5xl lg:text-6xl xl:text-7xl">
            Christmas
          </h1>
          <h1 class="text-xs sm:text-base lg:text-lg">with</h1>
          <h1 class="text-xl sm:text-5xl lg:text-6xl xl:text-7xl">
            Christ
          </h1>
        </div>
      </div>
    </div>

    <Navigation></Navigation>
  </div>
</template>

<script>
import Navigation from '@/components/Navigation/Navigation';
export default {
  components: { Navigation },
};
</script>

<style>
@font-face {
  font-family: 'TrajanRegular';
  src: local('TrajanRegular'),
    url(./assets/fonts/TrajanPro3Regular.ttf) format('truetype');
}

@font-face {
  font-family: 'TrajanBold';
  src: local('TrajanBold'),
    url(./assets/fonts/TrajanPro3Bold.ttf) format('truetype');
}

h1 {
  font-family: 'TrajanRegular', serif;
}

h2 {
  font-family: 'TrajanBold', serif;
}
</style>

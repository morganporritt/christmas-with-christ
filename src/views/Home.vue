<template>
  <div class="home -mt-16 md:-mt-24 lg:-mt-36">
    <div class="wrapper relative">
      <Splide :options="slideOptions" has-slider-wrapper>
        <SplideSlide v-for="day in days" :key="day.id">
          <div class="px-5 sm:px-8 md:px-16 pb-10">
            <Day
              :title="day.title"
              :date-string="day.dateString"
              :video-src="day.videoSrc"
              :video-file="day.videoFile"
              :video-src2="day.videoSrc2"
              :video-src3="day.videoSrc3"
              :video-src4="day.videoSrc4"
              :questions="day.questions"
              :additional-study-link="day.additionalStudyLink"
              :scriptures="day.scriptures"
              :time-permits="day.timePermits"
            ></Day>
          </div>
        </SplideSlide>
        <template #after-track>
          <div class="splide__autoplay">
            <button class="splide__play">Play</button>
            <button class="splide__pause">Pause</button>
          </div>
        </template>
      </Splide>
    </div>
  </div>
</template>

<script>
import Day from '@/components/Day/Day';
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import '@splidejs/splide/dist/css/splide.min.css';

export default {
  name: 'Home',
  components: {
    Day,
    Splide,
    SplideSlide,
  },
  setup() {
    function currentDayOfTheMonth() {
      const current = new Date();
      // console.log('Month: ', current.getMonth());
      // If not December then just return 0 here to show first slide.
      if (current.getMonth() != 11) {
        return 0;
      }
      return current.getDate() - 1;
    }

    const slideOptions = {
      speed: 200,
      easing: 'cubic-bezier(0.25, 1, 0.5, 1)',
      interval: 10000,
      lazyLoad: true,
      pagination: false,
      drag: true,
      dragMinThreshold: {
        mouse: 0,
        touch: 10,
      },
      perMove: 1,
      start: currentDayOfTheMonth(), // need this to be dynamic with currentDayOfTheMonth()
    };

    return { slideOptions };
  },
  data() {
    const daysData = require('../data/days.json');
    return {
      days: daysData.days,
    };
  },
};
</script>

<style>
.splide__arrows {
  position: absolute;
  width: 20rem;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  top: 12px;
}

.splide__arrow svg {
  fill: #696969;
}

.splide__arrow svg:hover {
  fill: #adadad;
}

.splide__arrow {
  background: none;
}

.page_banner_image {
  max-height: 300px;
}

@media (min-width: 425px) {
  .page_banner_image {
    max-height: 400px;
  }
}

@media (min-width: 640px) {
  .page_banner_image {
    max-height: 400px;
  }
}

@media (min-width: 768px) {
  .page_banner_image {
    max-height: 500px;
  }
  .splide__arrows {
    width: 30rem;
    top: 17px;
  }
  .splide__arrow svg {
    height: 2em;
    width: 2em;
  }
}

@media (min-width: 1024px) {
  .page_banner_image {
    max-height: 700px;
  }
}

@media (min-width: 1280px) {
  .page_banner_image {
    max-height: 800px;
  }
}

@media (min-width: 1536px) {
  .page_banner_image {
    max-height: 850px;
  }
}
</style>

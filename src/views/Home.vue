<template>
  <div class="home">
    <div class="wrapper relative">
      <Splide :options="slideOptions" has-slider-wrapper>

        <SplideSlide v-for="day in days" :key="day.id">
          <div class="px-5 sm:px-8 md:px-16 pb-10">
            <Day
                :title="day.title"
                :date-string="day.dateString"
                :video-src="day.videoSrc"
                :questions="day.questions"
                :additional-study-link="day.additionalStudyLink"
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

import Day from "@/components/Day/Day";
import {Splide, SplideSlide} from '@splidejs/vue-splide'
import '@splidejs/splide/dist/css/splide.min.css';

export default {
  name: 'Home',
  components: {
    Day,
    Splide,
    SplideSlide,
  },
  setup() {
    const slideOptions = {
      speed: 2000,
      easing: 'cubic-bezier(0.25, 1, 0.5, 1)',
      interval: 12000,
      lazyLoad: true,
      pagination: false,
      start: 0,
    };

    return { slideOptions };
  },
  methods: {
    currentDayOfTheMonth: function () {
      const current = new Date();
      return current.getDate();
    }
  },
  data () {
    return {
      days: [
        {
          id: 1,
          dateString: 'December 1st',
          title: 'Light of the World',
          videoSrc: "https://www.youtube.com/embed/8EKydaZFiQk?autoplay=1&mute=0",
          additionalStudyLink: "https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-light-of-the-world?lang=eng",
          questions: [
            'How has Jesus Christ been a light to you? To your family? (1 Nephi 17:13)',
            'What promises has Jesus made to those who follow his light?',
            'How can you be a light to others (3 Nephi 18:24)?'
          ],
        },
        // {
        //   id: 2,
        //   dateString: 'December 2nd',
        //   title: 'A Savior is Born',
        //   videoSrc: "https://www.youtube.com/embed/q_TEOyhy7Bg?autoplay=1&mute=0",
        //   additionalStudyLink: "https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-firstborn?lang=eng",
        //   questions: [
        //     'Read First Born in the Bible Dictionary. <a class="underline" href="https://www.churchofjesuschrist.org/study/scriptures/bd/firstborn?lang=eng">Link</a>',
        //     'What inheritance did Jesus receive as the First Born of the Father?',
        //     'What birthright blessings do we inherit as children of God?',
        //     'Spend a few minutes sharing memories about the first born of your family.'
        //   ],
        // },


      ],
    }
  },

}
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
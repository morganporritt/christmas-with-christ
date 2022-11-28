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
      return current.getDate() - 1;
    }

    const slideOptions = {
      speed: 500,
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
    return {
      days: [
        {
          id: 1,
          dateString: 'December 1st',
          title: 'Light of the World',
          videoSrc: 'https://www.youtube.com/embed/8EKydaZFiQk',
          videoSrc2: 'https://www.youtube.com/embed/b8jzdJCbXzc',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-light-of-the-world?lang=eng',
          questions: [
            'How has Jesus Christ been a light to you? To your family? (1 Nephi 17:13)',
            'What promises has Jesus made to those who follow his light?',
            'How can you be a light to others (3 Nephi 18:24)?',
          ],
        },
        {
          id: 2,
          dateString: 'December 2nd',
          title: 'First Born',
          videoSrc: 'https://www.youtube.com/embed/q_TEOyhy7Bg',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-firstborn?lang=eng',
          questions: [
            'Read First Born in the Bible Dictionary. <a class="underline" href="https://www.churchofjesuschrist.org/study/scriptures/bd/firstborn?lang=eng">Link</a>',
            'What inheritance did Jesus receive as the First Born of the Father?',
            'What birthright blessings do we inherit as children of God?',
            'Spend a few minutes sharing memories about the first born of your family.',
          ],
        },
        {
          id: 3,
          dateString: 'December 3rd',
          title: 'Prophesies',
          videoSrc: 'https://www.youtube.com/embed/ZI4da2p14M8',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-prophecies-about?lang=eng',
          questions: [
            'What is the purpose of prophecies?',
            'What prophecies should have helped people to recognize Jesus was the promised Savior and Redeemer?',
            'What prophecies about His second coming should we be looking for?',
            'How are prophecies evidence of God’s love?',
          ],
        },
        {
          id: 4,
          dateString: 'December 4th',
          title: 'Foreordained',
          videoSrc: 'https://www.youtube.com/embed/syjWhWQclck',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-foreordained?lang=eng',
          questions: [
            'What are some of the things Jesus was foreordained to do?',
            'What does your patriarchal blessing indicate are things you may have been foreordained to accomplish while in mortality?',
            'What things do you think your family was foreordained to do?',
          ],
        },
        {
          id: 5,
          dateString: 'December 5th',
          title: 'Creator',
          videoSrc: 'https://www.youtube.com/embed/-pd_1-y73bA',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-creator?lang=eng',
          questions: [
            'What difference does it make knowing that Christ created all things?',
            'What do we learn about Jesus Christ when we think about all that He has created?',
            'What are a few of your favorite creations?',
          ],
        },
        {
          id: 6,
          dateString: 'December 6th',
          title: 'Love of Jesus Christ',
          videoSrc: 'https://www.youtube.com/embed/FYVvE4tr2BI',
          // additionalStudyLink: "https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-creator?lang=eng",
          questions: [
            'What examples can you think of in scriptures where the love of Jesus Christ was manifest?',
            "When have you seen the love of Christ in your life or in your family's life?",
            'How does Jesus Christ expect us to treat other people?  (John 13:34-35)',
          ],
          scriptures: [
            {
              text: '2 Nephi 26:24',
            },
            {
              text: 'John 15:9, 13',
            },
            {
              text: 'Romans 8:35, 39',
            },
          ],
        },
        {
          id: 7,
          dateString: 'December 7th',
          title: 'Exemplar',
          videoSrc: 'https://www.youtube.com/embed/O0YNVqEYlkU',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-exemplar?lang=eng',
          questions: [
            'Moroni 7:48 What does it mean to be a TRUE FOLLOWER of Jesus Christ?',
            'Several scriptures talk about how Christ is our example. When has someone inspired you in a Christ-like way?',
            'In what way is your example leading people to Christ?',
            'What characteristic of Christ do I need to work on the most to become more like Him?',
            'Which family member has been a good example to you?',
          ],
        },
        {
          id: 8,
          dateString: 'December 8th',
          title: 'Lamb of God',
          videoSrc: 'https://www.youtube.com/embed/dqeQIp7bFac',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-lamb-of-god?lang=eng',
          questions: [
            'When an angel appears to Nephi he uses the title “Lamb” 56 times in four chapters. (1 Nephi 11-14) Of all the titles the angel could have used to refer to Jesus Christ, why do you think he chose that one?',
            'Would your family give you the title of a lamb or a lion? Are you a peacemaker or a peacebreaker?',
          ],
        },
        {
          id: 9,
          dateString: 'December 9th',
          title: 'Appearances, Antemortal',
          videoSrc: 'https://www.youtube.com/embed/tktmOxbZz0A',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-appearances-antemortal?lang=eng',
          questions: [
            'What does the word antemortal mean?',
            'In Ether 3:6 the Brother of Jared saw the finger of the Lord. When have you seen the hand of the Lord in your life? In the life of your family?',
          ],
        },
        {
          id: 10,
          dateString: 'December 10th',
          title: 'Trials of Christ',
          videoSrc: 'https://www.youtube.com/embed/y22ItxCz0_k',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-trials-of?lang=eng',
          questions: [
            'Read D&C 122: 4-8 In these verses, Jesus Christ tells Joseph Smith about some of the trials he may have to pass through.  In reality, the Lord was sharing with Joseph some of the things He Himself would pass through during the last 24 hours of his life.  See if you can identify some of the things the Savior suffered from Gethsemane to Calvary described in these verses.',
            'What can we learn from the Savior’s example about how we can respond during our own difficult trials?',
          ],
        },
        {
          id: 11,
          dateString: 'December 11th',
          title: 'Baptism of Christ',
          videoSrc: 'https://www.youtube.com/embed/9_dr9njVzKM',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-baptism-of?lang=eng',
          questions: [
            'What can we learn about our own baptism as we study Christ’s baptism and why He chose to be baptized? 2 Nephi 31:5-7',
            'Share a memory from each family member’s baptism day.',
          ],
        },
        {
          id: 12,
          dateString: 'December 12th',
          title: 'Taking the Name of Christ',
          videoSrc: 'https://www.youtube.com/embed/YR5rN7agKSE',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-taking-the-name-of?lang=eng',
          questions: [
            'What are the promised blessings for taking upon us the name of Christ?',
            'Jesus goes by many different names and titles in the scriptures.  As you partake of the sacrament this week, pick one of those names or titles, research its meaning and then seek to take that name upon you during the coming week.  Example: Bread of Life - prayerfully consider how you might feed others spiritually during the week.  Find spiritually hungry people and help them find the Bread of Life.',
          ],
        },
        {
          id: 13,
          dateString: 'December 13th',
          title: 'Good Shepherd',
          videoSrc: 'https://www.youtube.com/embed/lgAvr-tEgU0',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-good-shepherd?lang=eng',
          questions: [
            'According to these scriptures, what makes a good shepherd?',
            'What makes a good sheep?',
            'How can we be good shepherds?',
            'Share a time when a family member shepherded you or your family.',
          ],
        },
        {
          id: 14,
          dateString: 'December 14th',
          title: 'Glory of Christ',
          videoSrc: 'https://www.youtube.com/embed/8qEDZmQB5yk',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-glory-of?lang=eng',
          questions: [
            'Read Moses 1:1, 9-25',
            'How did experiencing Christ’s glory help Moses?',
            'How does Doctrine and Covenants 93:36-40 help you understand the glory of God, and how you can acquire his glory today?',
            'Prayerfully ponder those things in your life that may be causing a spiritual eclipse in your life. Determine how to best remove those things that are blocking light and truth from flowing into your life.',
          ],
        },
        {
          id: 15,
          dateString: 'December 15th',
          title: 'Mission of Christ',
          videoSrc: 'https://www.youtube.com/embed/mztp74-kx0Q',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-mission-of?lang=eng',
          questions: [
            'How have you seen the mission of Jesus Christ fulfilled in your life or in the life of those around you?',
            'What is your mission?',
            'Share a mission story from a family member.',
          ],
        },
        {
          id: 16,
          dateString: 'December 16th',
          title: 'Power of Christ',
          videoSrc: 'https://www.youtube.com/embed/BZqTRSVA1YA',
          videoSrc2: 'https://www.youtube.com/embed/coef8G5ax6E',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-power-of?lang=eng',
          questions: [
            'How have you seen the power of God in our family?',
          ],
        },
        {
          id: 17,
          dateString: 'December 17th',
          title: 'Redeemer',
          videoSrc: 'https://www.youtube.com/embed/d7N5QDDboi8',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-redeemer?lang=eng',
          questions: [
            'What does the word Redeemer mean?',
            'How have you been redeemed? What was the cost of your redemption?',
          ],
        },
        {
          id: 18,
          dateString: 'December 18th',
          title: 'Relationship with the Father',
          videoSrc: 'https://www.youtube.com/embed/4qR-vaMPFog',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-relationships-with-the-father?lang=eng',
        },
        {
          id: 19,
          dateString: 'December 19th',
          title: 'Atonement Through Christ',
          videoSrc: 'https://www.youtube.com/embed/oXrOG02NMB0',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-atonement-through?lang=eng',
          questions: [
            'How can you show appreciation for what the Saviors has done for you?',
            'Share your feelings for the atonement of Jesus Christ with your family.',
            'How has the atonement of the Savior helped you to become at-one with God, your family, and your ward?',
          ],
        },
        {
          id: 20,
          dateString: 'December 20th',
          title: 'Crucifixion of Christ',
          videoSrc: 'https://www.youtube.com/embed/nlALmOx8Sk0',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-atonement-through?lang=eng',
          questions: [
            "Commentary: Tad R. Callister But why the cross? Why not stoning or some other form of death? The cross was considered the most terrible form of death man could inflict upon man. It was said by President J. Reuben Clark Jr. 'to have been the most painful [death] that the ancients could devise.' It held the victim for hours at the brink of life, never quite releasing him, yet all the while inflicting upon the nerves and senses all he could painfully and consciously endure. It took man to his threshold of pain, but not beyond. Throbbing, pulsating pain was felt by a victim who would welcome death, but could find no such early relief. The Savior would nobly endure the cross, all that man could endure, and much, much more (“The Infinite Atonement,” Deseret Book, [2000])",
            'What crosses have you been asked to bear?',
            'What are you doing to carry your cross daily?',
            'Share a moment of agony you’ve experienced and how the Savior strengthened you to endure.',
          ],
        },
        {
          id: 21,
          dateString: 'December 21st',
          title: 'Death of Christ',
          videoSrc: 'https://www.youtube.com/embed/EpFhS0dAduc',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-death-of?lang=eng',
          questions: [
            'What blessings come because Jesus died for us?',
            'What kinds of things can become dead and buried in your life because of a Savior who was willing to die for you?',
            'What memories from a family funeral do you have?',
          ],
        },
        {
          id: 22,
          dateString: 'December 22nd',
          title: 'Resurrection',
          videoSrc: 'https://www.youtube.com/embed/fGCbMEmpY4g',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-resurrection?lang=eng',
          questions: [
            'How has your life become new and renewed since your coming to Christ?',
            'If you could witness the resurrection of one family member, who would you choose?',
          ],
        },
        {
          id: 23,
          dateString: 'December 23rd',
          title: 'Appearances, Post Mortal',
          videoSrc: 'https://www.youtube.com/embed/pUb1Kwlgitw',
          videoSrc2: 'https://www.youtube.com/embed/F9-2vPFtL_c',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-appearances-postmortal?lang=eng',
          questions: [
            'What does the Savior frequently do when He appears to God’s children?',
            'Why do you think He does that?',
            'What would be the first thing he would say to you if he were to appear today?',
          ],
          timePermits: true,
        },
        {
          id: 24,
          dateString: 'December 24th',
          title: 'Only Begotten Son',
          videoSrc: 'https://www.youtube.com/embed/5tb7kA3ubz8',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-only-begotten-son?lang=eng',
          questions: [
            'What is the relationship between grace and truth?',
            'What is the link between grace and truth and the Only Begotten Son?',
            'In what ways are you filled with grace and truth?',
            'Eleven times in scripture the phrase “grace and truth” are used to describe the Only Begotten Son.',
          ],
        },
        {
          id: 25,
          dateString: 'December 25th',
          title: 'Birth of Christ',
          videoSrc: 'https://www.youtube.com/embed/yXWoKi5x3lw',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-birth-of?lang=eng',
          questions: [
            'What is a truth from these verses you feel could help your life? How?',
            'Parents, share memories of the day each of your children were born.',
          ],
        },
        {
          id: 26,
          dateString: 'December 26th',
          title: 'Rock',
          videoSrc: 'https://www.youtube.com/embed/mLLXX8CJC6Y',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-rock?lang=eng',
          questions: [
            'After reading, consider why a rock is a good symbol for Christ.',
            'Are you a rock that the Savior can rely upon to build his church in our day?',
            'Which family member has been a ‘rock’ for you?',
          ],
        },
        {
          id: 27,
          dateString: 'December 27th',
          title: 'Savior',
          videoSrc: 'https://www.youtube.com/embed/3TH3w2LU0ck',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-savior?lang=eng',
          questions: [
            'The second question in the temple recommend interview states “Do you have a testimony of the Atonement of Jesus Christ and of His role as your Savior and Redeemer.” What is the difference between Savior and Redeemer?',
            'How have you been saved by the Savior?',
            'What have you been saved from?',
          ],
        },
        {
          id: 28,
          dateString: 'December 28th',
          title: 'Bread of Life',
          videoSrc: 'https://www.youtube.com/embed/vci5QPRvSQk',
          videoSrc2: 'https://www.youtube.com/embed/2eMJ6ZDCAp4',
          videoSrc3: 'https://www.youtube.com/embed/tJKmXtoMI5s',
          videoSrc4: 'https://www.youtube.com/embed/9kbgg7OT3TI',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/gs/bread-of-life?lang=eng',
          questions: [
            'After reading, consider why bread is a good symbol for Christ.',
            'How are you partaking of the bread of Christ daily?',
            'Which "ingredients" make up the "recipe" of your family?',
          ],
        },
        {
          id: 29,
          dateString: 'December 29th',
          title: 'Head of the Church',
          videoSrc: 'https://www.youtube.com/embed/MG9oCvaeBwM',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-head-of-the-church?lang=eng',
          questions: [
            'Look how often does the Lord use the phrase “my church” in these verses of scripture?',
            'What scripture would you share with someone who claims there isn’t just one true church on the earth today?',
            'Role play that discussion with another family member. What are you doing that allows the Savior to be the “head” of your life?',
            'What have you appreciated most about the head of your family?',
          ],
        },
        {
          id: 30,
          dateString: 'December 30th',
          title: 'Second Coming',
          videoSrc: 'https://www.youtube.com/embed/aCkWiiF5XlU',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/jesus-christ-second-coming?lang=eng',
          questions: [
            'What could be an important question these scriptures can answer about the second coming of Christ?',
            'When will be the time that you can allow the Savior to come into your life?',
            'Which family member are you most excited to reunite with at the Second Coming?',
          ],
        },
        {
          id: 31,
          dateString: 'December 31st',
          title: 'The Living Christ – The Testimony of the Apostles',
          videoSrc: 'https://www.youtube.com/embed/9ddXNF29goo',
          additionalStudyLink:
            'https://www.churchofjesuschrist.org/study/scriptures/tg/apostles?lang=eng',
          questions: [
            'Elder Robert D. Hales said in 2013, “The world is moving away from the Lord faster and farther than ever before. The adversary has been loosed upon the earth. We watch, hear, read, study, and share the words of prophets to be forewarned and protected. ‘The Living Christ: The Testimony of the Apostles’ was prepared in advance of when we will need it most (“Strengthening Faith and Testimony,” Ensign, Nov. 2013).”',
            'In what ways do you think we will need the teachings of The Living Christ in the days to come?',
            'In what ways have the teachings from The Living Christ blessed your life already?',
            'Do you have a similar testimony of the living Christ?',
            'Share your testimony of Jesus Christ with your family.',
          ],
        },
      ],
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

<template>
    <div class="Day">
      <h1 class="text-gray-50 text-center mb-8 text-2xl md:text-4xl">{{dateString}}</h1>
      <div class="w-full">


        <div class="bg-gray-800 p-3 rounded-lg max-w-4xl mx-auto">
          <h2 class="text-gray-50 text-center mb-8 text-2xl md:text-4xl p-3 rounded-lg bg-blue-900 bg-opacity-75">{{title}}</h2>

          <div class="video-wrap">
            <div class="video-container">
              <iframe
                  width="560" height="315"
                  :src="videoSrc"
                  allowfullscreen
              >
              </iframe>
            </div>
          </div>

          <h3 v-if="timePermits" class="text-gray-50 text-center text-sm">If time permits this is the one hour video of Christ’s post mortal appearance to the Nephites</h3>

          <div class="video-wrap" v-if="videoSrc2">
            <div class="video-container">
              <iframe
                  width="560" height="315"
                  :src="videoSrc2"
                  allowfullscreen
              >
              </iframe>
            </div>
          </div>

          <div class="video-wrap" v-if="videoSrc3">
            <div class="video-container">
              <iframe
                  width="560" height="315"
                  :src="videoSrc3"
                  allowfullscreen
              >
              </iframe>
            </div>
          </div>

          <div class="video-wrap" v-if="videoSrc4">
            <div class="video-container">
              <iframe
                  width="560" height="315"
                  :src="videoSrc4"
                  allowfullscreen
              >
              </iframe>
            </div>
          </div>

          <h1 v-if="questions" class="text-gray-50 text-center my-8 text-xl md:text-3xl">Questions to Ponder</h1>

          <div class="w-full" v-if="questions">
            <ul class="text-gray-50 list-disc ml-5 max-w-lg md:mx-auto">
              <li
                  v-html="question"
                  v-for="question in questions"
                  v-bind:key="question"
                  class="mb-3"
              >
              </li>
            </ul>
          </div>

          <a v-if="additionalStudyLink" :href="additionalStudyLink" class="underline text-gray-50 md:text-xl">
            <h1 class="text-gray-50 text-center my-8">Additional Scripture Study</h1>
          </a>

          <div v-if="scriptures">
            <h1 class="text-gray-50 text-center my-8 text-xl md:text-3xl">Additional Scripture Study</h1>

            <div class="w-full">
              <ul class="text-gray-50 ml-5 max-w-xl md:mx-auto flex flex-col gap-1 justify-center w-full">
                <li
                    v-for="scripture in scriptures"
                    v-bind:key="scripture"
                    class="mb-3 w-max"
                >
                  {{scripture.text}}
                </li>
              </ul>
            </div>

          </div>

        </div>
      </div>
    </div>



</template>

<script>
    export default {
        name: 'Day',
      props: {
        title: String,
        dateString: String,
        videoSrc: String,
        videoSrc2: String,
        videoSrc3: String,
        videoSrc4: String,
        questions: Array,
        additionalStudyLink: String,
        scriptures: Array,
        timePermits: Boolean,
      },
    };
</script>

<style>
  iframe {
    max-width: 100%;
  }

  .video-container {
    position: relative;
    overflow: hidden;
    height: 0;
    padding-bottom: 56.25%;
  }

  .video-container iframe{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }


  .video-wrap {
    width: 100%;
    max-width: 900px;
    margin: 20px auto;
  }
</style>

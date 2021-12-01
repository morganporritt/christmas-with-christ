<template>
    <div class="Navigation">
      <div id="nav" class="absolute top-0 z-10 bg-gray-100 bg-opacity-10 w-full flex flex-row justify-center py-3">

        <div
            v-for="item in navigationItems"
            v-bind:key="item.id"
        >
          <router-link
              :to="{path:item.href}"
              class="text-gray-50 px-3 hover:text-gray-500 sm:text-lg sm:px-5"
          >
            {{item.text}}
          </router-link>
        </div>
      </div>
      <router-view/>
    </div>
</template>

<script>
    export default {
        name: 'Navigation',
        data ()
        {
          return {
            navigationItems: [
              {
                id: 1,
                text: 'Home',
                href: '/',
              },
              {
                id: 2,
                text: 'Quotes',
                href: '/quotes',
              },
              {
                id: 3,
                text: 'More',
                href: '/more',
              },
            ]
          }
        }
    };
</script>

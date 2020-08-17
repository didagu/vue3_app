<template>
  <div>
    <app-layout
      :no-toolbar="!showToolbar"
      :show-banner="showBanner"
      no-main-padding
    >
      <template #banner>
        <div
          class="banner"
          style="flex-grow: 1;padding: 8px; align-self: center; display: flex;align-content:center;"
        >
          <marquee>
            This is the end!!!! Finally somebody is using
            Marqueeeeeeeeeeeeeeeeeeeeeee! Super promo: buy 2 abas web devs,
            get one for free!
          </marquee>
        </div>
      </template>
      <h1>My Event</h1>
      <p>Capacity: {{ capacity }}</p>
      <button @click="increaseCapacity()">Increase Capacity</button>
    </app-layout>
  </div>
</template>

<script>
import AppLayout from '@abas/elements/src/components/AppLayout.vue';
import { ref } from 'vue'; // <-- Use this line if you're in a Vue 3 app

export default {
  name: 'App',
  components: {
    AppLayout,
  },
  setup() {
    const capacity = ref(3);
    const showToolBar = ref(true);
    const showBanner = ref(true);

    function increaseCapacity() {
      capacity.value += 1;
    }

    return {
      capacity,
      showToolBar,
      showBanner,
      increaseCapacity,
    };
  },
};
</script>

<template>
  <div class="about">
    <h1>This is the newfeed page</h1>
    <newsFeed/>
    <!--<button>Create Post</button>-->
  </div>
</template>

<script lang ="ts">
import { defineComponent } from 'vue';
import newsFeed from '@/components/newsFeed.vue';

export default defineComponent({
  components: {
    newsFeed,
  },
  setup() {
    return {};
  },
});

</script>

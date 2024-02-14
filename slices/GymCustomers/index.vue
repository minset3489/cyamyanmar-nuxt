<script setup lang="ts">
import { type Content } from "@prismicio/client";

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(
  getSliceComponentProps<Content.GymCustomersSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ]),
);
</script>

<template>
  <Bounded
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
  <PrismicRichText class="text-center heading heading--lg mb-6 md:mb-8" :field="slice.primary.heading" />

  <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6 md:gap-7 lg:gap-8">
    <div
        v-for="item of slice.items"
        :key="item.name ?? ''"
        class="mx-auto text-center"
      >
      <PrismicImage class="rounded-md drop-shadow-lg" :field="item.image" />
      <div class=" mx-auto heading heading--sm m-4">{{item.name}}</div>
    </div>
  </div>

  </Bounded>
</template>

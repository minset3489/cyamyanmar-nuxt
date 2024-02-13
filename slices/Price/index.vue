<script setup lang="ts">
import { type Content } from "@prismicio/client";

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(
  getSliceComponentProps<Content.PriceSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ]),
);

const packages = ref([
  {title : 'Standard', price : '600,000', 
  services : [ 'Next Year Costing 200 USD/ yr', 'Storage Space 500MB', 'Webmail Account 5', 'Re-Designing', 'SSL Certificate', 'Google Analytics Reports', ]},
  {title : 'Professional', price : '1,500,000', 
  services : [ 'Next Year Costing 500 USD/ yr', 'Storage Space 500MB', 'Webmail Account 5', 'Re-Designing', 'SSL Certificate', 'Google Analytics Reports', 'Premium Technical Support', 'Access to All Plugins' ]},
  {title : 'Business', price : '850,000', 
  services : [ 'Next Year Costing 350 USD/ yr', 'Storage Space 500MB', 'Webmail Account 5', 'Re-Designing', 'SSL Certificate', 'Google Analytics Reports',  ]},
  
])

</script>

<template>
  <Bounded
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
  <PrismicRichText class="heading heading--md mb-12 text-center" :field="slice.primary.heading" />

  <div class="grid grid-cols-1 md:grid-cols-3  mx-auto  place-items-center font-body">
    <div
        v-for="p of packages"
        :key="p.title ?? ''"
        class="grid sm:place-items-start rounded-md md:rounded-none place-items-center sm:text-left text-center border border-slate-400 mt-6 md:mt-0"
      >
      <div class="bg-gradient-to-tr from-gray-500 to-cyan-200 text-center w-full p-4 " 
        :class="{'!bg-gradient-to-tr !from-cyan-400 !to-emerald-400': p.title=== 'Professional' }"
        >
        <p class="heading heading--md !text-slate-600">{{ p.title }}</p>
        <p class="heading heading--sm !text-white mt-1">First Year Costing</p>
      </div>
      <div class="w-full text-center  border-y border-slate-400">         
          <p class="text-xl p-4">
            MMK 
            <span class="text-3xl md:text-5xl text-emerald-600 font-semibold">{{ p.price }}</span> 
            / Year</p>
      </div>
      <div class="flex px-8 py-2 bg-white w-full" v-for = "service in p.services" :key="service">
        <p><span class="text-green-500 text-2xl mr-2">●</span>{{ service }}</p>
      </div>
    </div>

  </div>

  </Bounded>
</template>

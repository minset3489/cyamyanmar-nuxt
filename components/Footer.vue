<script setup>


const settings = useSettings()

</script>
<template>
    <Bounded as="footer" class="!py-4 md:!py-6 lg:!py-8">

<div class="mx-auto text-center text-2xl text-slate-500 border-t border-slate-400 border-opacity-15 pt-4 pb-2 md:pb-0 mt-4 ">
Created by <span class="text-green-700">Min Set</span> | All rights reserved!
</div>

        <!-- <div class="flex gap-4 items-center justify-between flex-col sm:flex-row">
            <CyaLogo/>
            <p class="text-xs">Created by {{ settings?.data.site_title }} {{new Date().getFullYear()}}</p>
            <nav>
                <ul class="flex">
                    <li
                    v-for="item of settings?.data.navigation"
                    :key="item.label ?? ''"
                    >
                        <PrismicLink :field="item.link" class="p-4 ">
                            {{ item.label }}
                        </PrismicLink>
                    </li>
                </ul>
            </nav>
        </div> -->
    </Bounded>
</template>
<script setup>


const settings = useSettings()

</script>
<template>
    <div class="sticky top-0 left-0 right-0 z-50 bg-white bg-opacity-50">
    <Bounded as="header" class="!py-0 md:!py-4 ">
        <div class="flex md:gap-4 items-center justify-between flex-col sm:flex-row ">
            <CyaLogo class="w-[80px] md:w-[120px] h-[60px] md:h-[90px] p-0 m-0 "/>
            <nav class="flex place-items-center">
                <ul class="flex text-center ">
                    <li v-for="item of settings?.data.navigation"
                    :key="item.label ?? ''"
                    >
                        <PrismicLink :field="item.link" class="hover:bg-gradient-to-tr  hover:font-semibold hover:from-cyan-200  hover:to-emerald-300 rounded-lg py-3 px-3 mr-1 !text-[.9rem] md:!text-base transition-colors duration-200 ease-in-out ">
                            {{ item.label }}
                        </PrismicLink>
                    </li>
                </ul>
                <NuxtLink
                    :field="settings?.data.button_link"
                    class="button cursor-pointer text-center !text-xs md:!text-base !py-2 md:!py-2 !px-4 md:!px-6"
                    >
                    {{ settings?.data.button_text }}
                </NuxtLink>
            </nav>
        </div>
    </Bounded>
    </div>
</template>
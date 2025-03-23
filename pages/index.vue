<template>
  <div>
    <header class="w-full shadow-sm">
      <div class="flex justify-between container mx-auto p-5">
        <div>
          <h1 class="font-semibold">SEAIT JOB HIRING</h1>
        </div>
        <div>
          <Icon
            class="cursor-pointer"
            @click="isDark = !isDark"
            :name="`carbon:${isDark ? 'moon' : 'sun'}`"
          />
        </div>
      </div>
    </header>
    <main class="container mx-auto w-full py-5">
      <div class="flex items-center justify-between w-full">
        <div class="size-full max-w-lg items-center justify-center overflow-hidden p-8">
          <BoxReveal color="#E1251B">
            <p class="text-[3.5rem] font-semibold">
              Inspira UI<span class="text-[#E1251B]">.</span>
            </p>
          </BoxReveal>

          <BoxReveal color="#E1251B" :duration="0.8">
            <h2 class="mt-[.5rem] text-[1rem]">
              Beautiful components for
              <span class="text-[#E1251B]">Vue &amp; Nuxt.</span>
            </h2>
          </BoxReveal>

          <BoxReveal color="#E1251B" :duration="1">
            <div class="mt-6">
              <p>
                -&gt; Free and open-source animated components built with
                <span class="font-semibold text-[#E1251B]"> Vue/Nuxt</span>,
                <span class="font-semibold text-[#E1251B]"> Typescript</span>,
                <span class="font-semibold text-[#E1251B]"> Tailwind CSS</span>, and
                <span class="font-semibold text-[#E1251B]"> motion-v</span>
                . <br />
                -&gt; 100% open-source, and customizable. <br />
                <InteractiveHoverButton
                  class="my-5"
                  text="Let's Begin"
                ></InteractiveHoverButton>
              </p>
            </div>
          </BoxReveal>
        </div>
        <PhotoGallery :items="items" />
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
const colorMode = useColorMode();
const isDark = computed({
  get() {
    return colorMode.value === "dark";
  },
  set() {
    colorMode.preference = colorMode.value === "dark" ? "light" : "dark";
  },
});

const items = [
  {
    src:
      "https://images.pexels.com/photos/16834200/pexels-photo-16834200/free-photo-of-young-brunette-in-a-white-dress-sitting-on-a-bench-and-holding-flowers.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/16834202/pexels-photo-16834202/free-photo-of-young-woman-in-a-white-dress-posing-outdoors.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/16834194/pexels-photo-16834194/free-photo-of-woman-in-white-dress-posing-with-red-flowers-on-lap.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/17362900/pexels-photo-17362900/free-photo-of-pretty-young-model-in-chinese-retro-dress.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/19447919/pexels-photo-19447919/free-photo-of-model-in-a-pink-ao-dai-dress-with-a-bouquet-of-tulips-by-the-river.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/20332975/pexels-photo-20332975/free-photo-of-young-woman-posing-in-a-silk-slip-dress.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/19732643/pexels-photo-19732643/free-photo-of-woman-in-white-dress-sitting-and-reading-book.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
  {
    src:
      "https://images.pexels.com/photos/17347482/pexels-photo-17347482/free-photo-of-woman-in-dress-posing-with-bag.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load",
  },
];
</script>

<template>
  <div>
    <header class="w-full shadow-sm fixed top-0 left-0 dark:bg-background bg-background z-50">
      <div class="flex justify-between container mx-auto p-3">
        <div class="flex gap-1 items-center">
          <!-- <svg-icon class="dark:bg-background" name="icon/logo" width="32" height="32"></svg-icon> -->
          <h1 class="font-semibold">SUPER<span class="text-emerald-600">HURE</span></h1>
        </div>
        <div>
          <Icon class="cursor-pointer" @click="isDark = !isDark" :name="`carbon:${isDark ? 'moon' : 'sun'}`" />
        </div>
      </div>
    </header>
    <main class="container mx-auto w-full py-5 mt-24">
      <div class="relative">
        <ClientOnly>
          <Tetris
            class="h-[300px] lg:h-[500px] w-full [mask-image:radial-gradient(450px_circle_at_center,#00C16A,transparent)]"
            :base="15" square-color="#777e7a" />
          <div class="flex items-center justify-between w-full absolute top-5">
            <div class="size-full max-w-lg items-center justify-center overflow-hidden p-8">
              <BoxReveal color="#1b1c1b">
                <p class="text-[1.5rem] font-semibold">
                  SEAIT Careers: Where Talent Meets Innovation<span class="text-[#1f864c]">.</span>
                </p>
              </BoxReveal>

              <BoxReveal color="#1b1c1b" :duration="1">
                <div class="mt-6">
                  <p>
                    Join us to
                    <span class="font-semibold text-[#1f864c]"> grow, innovate </span>
                    and <span class="font-semibold text-[#1f864c]">succeed</span> in a
                    <span class="font-semibold text-[#1f864c]">dynamic</span> work environment.

                  </p>
                  <InteractiveHoverButton class="my-5" text="Let's Begin"></InteractiveHoverButton>
                </div>
              </BoxReveal>
            </div>
            <PhotoGallery class="lg:block hidden" :items="items" />

          </div>
        </ClientOnly>
      </div>



      <!-- for joblist -->
      <div class="container flex flex-col mx-auto justify-center items-center max-w-sm lg:max-w-4xl mt-24 mb-8 gap-2">
        <h2 class="text-balance text-center text-2xl lg:text-3xl font-bold">
          SEAIT JOB OPPORTUNITIES
        </h2>
        <span class="text-sm text-center  text-gray-400">Unlock opportunities, build your future, and grow with SEAIT.</span>
      </div>
      <div class="container mx-auto w-full items-center justify-center px-8">
        <TracingBeam class="px-6">
          <BentoGrid class="mx-auto max-w-8xl">
            <BentoGridItem v-for="(item, index) in cardItem" :key="index">
              <template #header>
                <div class="flex size-full space-x-4">
                  <NuxtImg src="/images/hero.jpg"></NuxtImg>
                </div>
              </template>

              <template #title>
                <strong>{{ item.title }}</strong>
              </template>

              <!-- <template #icon> 
                <svg-icon class="cursor-pointer" name="icon/facebook" width="32" height="32"></svg-icon>
              </template> -->

              <template #description>
                <InteractiveHoverButton text="Review"></InteractiveHoverButton>
              </template>
            </BentoGridItem>
          </BentoGrid>
        </TracingBeam>
      </div>


    </main>

    <footer class="dark:bg-background bg-background mt-10 w-full shadow-lg border-t  px-3">
      <div class="container mx-auto flex justify-center items-center">
        <div class="flex flex-col justify-center items-center">
          <div class="flex py-4 gap-5 ">
            <a href="www.facebook.com" target="_blank"><svg-icon class="cursor-pointer" name="icon/facebook" width="32" height="32"></svg-icon></a>
            <a href="www.twitter.com" target="_blank"><svg-icon href="twitter.com" class="cursor-pointer" name="icon/twitter" width="32" height="32"></svg-icon></a>
            <a href="www.gmail.com" target="_blank"><svg-icon href="google.com" class="cursor-pointer" name="icon/mail" width="32" height="32"></svg-icon></a>
          </div>

          <p class="text-xs text-center">Copyright © 2020-2025. South East Asian Institute of Technology Inc. All Rights
            Reserved.
          </p>
          <p class="text-xs">Developed by: Jannnyy Tech Solutions</p>
        </div>

      </div>

    </footer>
  </div>
</template>

<script setup lang="ts">
definePageMeta({

});

useSeoMeta({
  title: "SEAIT JOB HIRING",
  description: "Testing",
  ogTitle: "SEAIT JOB HIRING",
  ogDescription: "Testing",
});
const colorMode = useColorMode();
const isDark = computed({
  get() {
    return colorMode.value === "dark";
  },
  set() {
    colorMode.preference = colorMode.value === "dark" ? "light" : "dark";
  },
});

const cardItem = [
  {
    title: "The Dawn of Innovation",
    description: "Explore the birth of groundbreaking ideas and inventions.",
  },
  {
    title: "The Digital Revolution",
    description: "Dive into the transformative power of technology.",
  },
  {
    title: "The Art of Design",
    description: "Discover the beauty of thoughtful and experience design.",
  },
  {
    title: "The Power of Communication",
    description: "Understand the impact of effective communication in our lives.",
  },
  {
    title: "The Pursuit of Knowledge",
    description: "Join the quest for understanding and enlightenment.",
  },
  {
    title: "The Joy of Creation",
    description: "Experience the thrill of bringing ideas to life.",
  },
  {
    title: "The Spirit of Adventure",
    description: "Embark on exciting journeys and thrilling discoveries.",
  },
];

const connectItems = [
  {
    id: 1,
    name: "John Doe",
    designation: "Software Engineer",
    image:
      "https://images.unsplash.com/photo-1599566150163-29194dcaad36?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3387&q=80",
  },
  {
    id: 2,
    name: "Robert Johnson",
    designation: "Product Manager",
    image:
      "https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8YXZhdGFyfGVufDB8fDB8fHww&auto=format&fit=crop&w=800&q=60",
  },
  {
    id: 3,
    name: "Jane Smith",
    designation: "Data Scientist",
    image:
      "https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NXx8YXZhdGFyfGVufDB8fDB8fHww&auto=format&fit=crop&w=800&q=60",
  },
  {
    id: 4,
    name: "Emily Davis",
    designation: "UX Designer",
    image:
      "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fGF2YXRhcnxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=800&q=60",
  },
  {
    id: 5,
    name: "Tyler Durden",
    designation: "Soap Developer",
    image:
      "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3540&q=80",
  },
  {
    id: 6,
    name: "Dora",
    designation: "The Explorer",
    image:
      "https://images.unsplash.com/photo-1544725176-7c40e5a71c5e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3534&q=80",
  },
];

const dummyContent = [
  {
    title: "Lorem Ipsum Dolor Sit Amet",
    description: [
      "Sit duis est minim proident non nisi velit non consectetur. Esse adipisicing laboris consectetur enim ipsum reprehenderit eu deserunt Lorem ut aliqua anim do. Duis cupidatat qui irure cupidatat incididunt incididunt enim magna id est qui sunt fugiat. Laboris do duis pariatur fugiat Lorem aute sit ullamco. Qui deserunt non reprehenderit dolore nisi velit exercitation Lorem qui do enim culpa. Aliqua eiusmod in occaecat reprehenderit laborum nostrud fugiat voluptate do Lorem culpa officia sint labore. Tempor consectetur excepteur ut fugiat veniam commodo et labore dolore commodo pariatur.",
      "Dolor minim irure ut Lorem proident. Ipsum do pariatur est ad ad veniam in commodo id reprehenderit adipisicing. Proident duis exercitation ad quis ex cupidatat cupidatat occaecat adipisicing.",
      "Tempor quis dolor veniam quis dolor. Sit reprehenderit eiusmod reprehenderit deserunt amet laborum consequat adipisicing officia qui irure id sint adipisicing. Adipisicing fugiat aliqua nulla nostrud. Amet culpa officia aliquip deserunt veniam deserunt officia adipisicing aliquip proident officia sunt.",
    ],
    badge: "Vue",
    image:
      "https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&q=80&w=3540&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    title: "Lorem Ipsum Dolor Sit Amet",
    description: [
      "Ex irure dolore veniam ex velit non aute nisi labore ipsum occaecat deserunt cupidatat aute. Enim cillum dolor et nulla sunt exercitation non voluptate qui aliquip esse tempor. Ullamco ut sunt consectetur sint qui qui do do qui do. Labore laborum culpa magna reprehenderit ea velit id esse adipisicing deserunt amet dolore. Ipsum occaecat veniam commodo proident aliqua id ad deserunt dolor aliquip duis veniam sunt.",
      "In dolore veniam excepteur eu est et sunt velit. Ipsum sint esse veniam fugiat esse qui sint ad sunt reprehenderit do qui proident reprehenderit. Laborum exercitation aliqua reprehenderit ea sint cillum ut mollit.",
    ],
    badge: "Nuxt",
    image:
      "https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&q=80&w=3540&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    title: "Lorem Ipsum Dolor Sit Amet",
    description: [
      "Ex irure dolore veniam ex velit non aute nisi labore ipsum occaecat deserunt cupidatat aute. Enim cillum dolor et nulla sunt exercitation non voluptate qui aliquip esse tempor. Ullamco ut sunt consectetur sint qui qui do do qui do. Labore laborum culpa magna reprehenderit ea velit id esse adipisicing deserunt amet dolore. Ipsum occaecat veniam commodo proident aliqua id ad deserunt dolor aliquip duis veniam sunt.",
    ],
    badge: "Inspira UI",
    image:
      "https://images.unsplash.com/photo-1469474968028-56623f02e42e?auto=format&fit=crop&q=80&w=3506&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
];

const items = [
  {
    src:
      "/images/1.jpg",
  },
  {
    src:
      "/images/2.jpg",
  },
  {
    src:
      "/images/3.jpg",
  },
  {
    src:
      "/images/4.jpg",
  },
  {
    src:
      "/images/5.png",
  },
  {
    src:
      "/images/6.jpg",
  },
  {
    src:
      "/images/7.jpg",
  },
  {
    src:
      "/images/8.jpg",
  },
];
</script>

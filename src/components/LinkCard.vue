<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  url: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    default: '',
  },
  icon: {
    type: String,
    default: 'flag',
  },
})

const icons = {
  flag: `<path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 12v9a1 1 0 0 1-2 0V4c0-1.1.9-2 2-2h6c1.1 0 1.999.9 1.999 2H18a2 2 0 0 1 2 2v6a2 2 0 0 1-2 2h-5a2 2 0 0 1-1.997-2zm0-8v6h7v2h5.002V6H12V4z"
        />`,
  code: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5"></path>',
  briefcase:
    '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 0 0 .75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 0 0-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0 1 12 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 0 1-.673-.38m0 0A2.18 2.18 0 0 1 3 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 0 1 3.413-.387m7.5 0V5.25A2.25 2.25 0 0 0 13.5 3h-3a2.25 2.25 0 0 0-2.25 2.25v.894m7.5 0a48.667 48.667 0 0 0-7.5 0M12 12.75h.008v.008H12v-.008Z"></path>',
  file: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.5 14.25v-2.625a3.375 3.375 0 0 0-3.375-3.375h-1.5A1.125 1.125 0 0 1 13.5 7.125v-1.5a3.375 3.375 0 0 0-3.375-3.375H8.25m2.25 0H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 0 0-9-9Z"></path>',
}
</script>

<template>
  <a
    :href="url"
    target="_blank"
    rel="noreferrer"
    class="group relative flex w-full items-center gap-4 rounded-xl border border-gray-800 bg-gray-900 p-4 shadow-md shadow-gray-900/75 transition-all duration-300 hover:scale-[1.02] hover:border-yellow-600 hover:shadow-xl hover:shadow-yellow-500/20"
  >
    <!-- Icon Container -->
    <div
      class="flex h-12 w-12 shrink-0 items-center justify-center rounded-lg bg-gray-800 text-yellow-500 transition-all duration-300 group-hover:scale-115 group-hover:bg-yellow-600 group-hover:text-white group-hover:shadow-xl group-hover:shadow-yellow-500/30"
    >
      <svg
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        class="h-6 w-6 transition-transform duration-300 group-hover:rotate-6"
        v-html="icons[icon] || icons.flag"
      ></svg>
    </div>

    <!-- Text Content-->
    <div class="min-w-0 flex-1">
      <h3 class="truncate font-display font-semibold text-white">{{ title }}</h3>
      <p class="truncate text-sm text-gray-500">
        {{ description }}
      </p>
    </div>

    <!-- Hover Glow Effect-->
    <div
      class="bgb-linear-to-r transition-opacity-100 absolute inset-0 rounded-xl from-yellow-500/0 via-yellow-500/10 to-yellow-500/0 opacity-0"
    />
  </a>
</template>

<!-- show only "default" and "quote" layout -->
<!-- hide the footer from Page 4 -->
<template>
  <footer
    v-if="$nav.currentLayout === 'default' || $nav.currentLayout === 'quote'"
    class="absolute bottom-0 left-0 right-0 p-2" style="font-size:small;font-weight: 100; color:#888"
  >
  {{ $nav.currentPage }} / {{ $nav.total }}
  </footer>
</template>
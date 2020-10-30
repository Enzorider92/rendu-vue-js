<template>
  <button class="bg-gray-500 text-white font-bold py-2 px-4 rounded hover:bg-gray-700">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "base-button",
  props: ['text']
}
</script>
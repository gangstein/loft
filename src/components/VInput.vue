<template>
  <input
    :value="value"
    type="text"
    :aria-label="label"
    :placeholder="label"
    @input="$emit('input', $event)"
  >
</template>

<script>
export default {
  name: 'VInput',

  props: {
    label: {
      type: String,
      default: 'text',
    },
    value: {
      type: String,
    }
  }
};
</script>

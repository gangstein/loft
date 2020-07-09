<template>
  <VInput
    v-if="getType === 'text'"
    class="field"
    :label="label"
    :value="value"
    @input="input"
  />

  <select
    v-else-if="getType === 'select'"
    class="field"
    :aria-label="label"
    :value="value"
    @input="input"
  >
    <option
      v-for="m in meta"
      :key="m.value"
    >
      {{m.value}}
    </option>
  </select>

  <VInput
    v-else-if="getType === 'date'"
    class="field"
    type="date"
    :value="value"
    @input="input"
  />

  <VInput
    v-else-if="getType === 'checkbox'"
    class="field"
    type="checkbox"
    :value="value"
    @input="input"
  />
</template>

<script lang="ts">
import Vue from 'vue';
import VInput from './VInput.vue';

export default Vue.extend({
  name: 'VField',
  components: { VInput },
  props: {
    type: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
    validate: {
      type: Function,
    },
    meta: {
      type: Array,
    },
  },

  computed: {
    getType() {
      switch (this.type) {
        case 'string':
          return 'text';
        case 'select':
          return 'select';
        case 'date':
          return 'date';
        case 'bool':
          return 'checkbox';
        default:
          return 'input';
      }
    },
  },

  methods: {
    input(e) {
      this.$emit('input', e.target.value)
    }
  }
});
</script>

<style scoped>
.field {
  width: 200px;
  height: 30px;
  box-sizing: border-box;
  border: 2px solid black;
  border-radius: 2px;
}
</style>

<template>
  <div>
    <div class="line" v-for="d in data" :key="d.id">
      <VField
        v-model="d[setting.field]"
        v-for="setting in settings"
        :key="setting.name"
        :type="setting.type"
        :label="setting.label"
        :meta="setting.meta"
        :validator="setting.validator"
        class="line__field"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import VField from './VField.vue';

export default Vue.extend({
  name: 'VTable',

  components: {
    VField,
  },
  props: {
    settings: {
      type: Array,
    },
    data: {
      type: Array,
    },
  },
});
</script>

<style>
.line {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 10px 0;
}

.line__field + .line__field {
  margin-left: 10px;
}
</style>

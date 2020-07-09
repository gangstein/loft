<template>
  <div id="app">
    <VTable
      :settings="settings"
      :data="data"
    />
  </div>
</template>

<script>
import VTable from '@/components/VTable';

export default {
  name: 'App',

  components: {
    VTable,
  },

  data() {
    return {
      settings: [
        {
          label: 'Name',
          field: 'name',
          type: 'string',
          validator: '',
        },
        {
          label: 'Gender',
          field: 'gender',
          type: 'select',
          validator: '',
          meta: [
            {
              label: 'Male',
              value: 'male',
            },
            {
              label: 'Female',
              value: 'female',
            },
          ]
        },
        {
          label: 'Subscription',
          field: 'sub',
          type: 'date',
          validator: '',
        },
      ],

      data: [
        {
          id: '8994fd59-a976-47bd-8118-8e7627a1c5c3',
          name: 'User name 1',
          gender: 'male',
          sub: '2020-03-04'
        },
        {
          id: '4ca67bc7-d47d-4855-b44a-0d7e7c8bcc46',
          name: 'User name 2',
          gender: 'female',
          sub: '2020-03-05'
        },
        {
          id: 'e3323e59-fb8f-4160-8888-eb69ae7e6fce',
          name: 'User name 3',
          gender: 'male',
          sub: '2020-03-06'
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

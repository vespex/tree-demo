<template>
  <div class="tree-demo">
    <v-tree :isRoot="true" :name="data.name" :children="data.children" />
  </div>
</template>

<script>
import { reactive } from 'vue';
import VTree from './components/Tree.vue';

export default {
  components: { VTree },
  setup(props) {
    const data = reactive({
      id: 1,
      name: '1',
      children: [
        {
          id: 11,
          name: '1-1',
          children: [
            {
              id: 111,
              name: '1-1-1',
              children: [
                { id: 1111, name: '1-1-1-1', children: [] },
                { id: 1112, name: '1-1-1-2', children: [] },
              ],
            },
            {
              id: 112,
              name: '1-1-2',
              children: [
                { id: 112, name: '1-1-2-1', children: [] },
                { id: 112, name: '1-1-2-2', children: [] },
              ],
            },
          ],
        },
        {
          id: 12,
          name: '1-2',
          children: [
            {
              id: 121,
              name: '1-2-1',
              children: [
                { id: 1211, name: '1-2-1-1', children: [] },
                { id: 1212, name: '1-2-1-2', children: [] },
              ],
            },
            {
              id: 122,
              name: '1-2-2',
              children: [
                { id: 1221, name: '1-2-2-1', children: [] },
                { id: 1222, name: '1-2-2-2', children: [] },
              ],
            },
          ],
        },
      ],
    });
    return { data };
  },
};
</script>

<style lang="less">
body {
  margin: 0;
}
#app {
  padding: 20px;
}
</style>

<template>
  <div class="v-tree" :class="{ 'root-node': isRoot }">
    <div class="v-tree-name">{{ name }}</div>
    <div class="v-tree-children">
      <v-tree
        :class="{ 'last-node': !item.children.length }"
        :key="item.id"
        :name="item.name"
        :children="item.children"
        v-for="item in children"
      />
    </div>
  </div>
</template>
<script>
export default {
  name: 'v-tree',
  props: {
    name: String,
    children: Array,
    isRoot: Boolean,
  },
};
</script>
<style lang="less">
.v-tree {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;

  &-name {
    border: 1px solid #000;
    padding: 10px 20px;
    margin: 10px 20px;
    position: relative;
    height: 30px;
    line-height: 30px;
    &::before,
    &::after {
      content: '';
      position: absolute;
      top: 50%;
      left: -21px;
      border-top: 1px solid #000;
      width: 21px;
    }
    &::after {
      left: auto;
      right: -21px;
    }
  }
  &-children {
    position: relative;
    &::before {
      content: '';
      position: absolute;
      right: 0px;
      top: 25%;
      border-left: 1px solid #000;
      height: 50%;
    }
  }
  &.last-node {
    .v-tree {
      &-name {
        &::before {
          display: none;
        }
      }
    }
  }
  &.root-node {
    > .v-tree-name {
      &::after {
        display: none;
      }
    }
  }
}
</style>

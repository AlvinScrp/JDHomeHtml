<template>
  <div class="intro-tab">
    <div
      class="tab-item"
      :class="[{ 'tab-item-active': isItemSelected(item.key) }]"
      v-for="item in tabs"
      :key="item.key"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tabs: Array,
    selectedKey: String,
  },
  components: {},
  data() {
    return {};
  },
  methods: {
    isItemSelected(itemKey) {
      return this.selectedKey === itemKey;
    },
  },
};
</script>
<style lang='scss' scoped>
.intro-tab {
  position: -webkit-sticky;
  position: sticky;
  z-index: 3;
  top: 40px;
  height: 49px;
  background-color: white;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  color: #212121;
  &::after {
    border: solid #f5f5f5;
    border-width: 0 0 1px 0;
    content: "\0020";
    left: 0;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    transform-origin: 0 0;
    z-index: 3;
  }
  .tab-item {
    height: 49px;
    display: inline-block;
    font-size: 14px;
    font-weight: 300;
    line-height: 49px;
    vertical-align: middle;
    min-width: 62px;
  }
  .tab-item-active {
    font-size: 16px;
    font-weight: 500;
    background-image: url("https://ad-dapp-osscp.qunarzz.com/ad_dapp_oss_oper/f4979d23d30700680bd1bf5174fc597c.png");
    background-size: auto 49px; /* 使背景图像覆盖整个元素 */
    background-position: left top; /* 将背景图像居中 */
    background-repeat: no-repeat; /* 防止背景图像重复 */
  }
}
</style>
<template>
<div class="home-link-entry">
  <div
    class="home-link-entry-item"
    v-for="(item, index) in list"
    :key="index"
  >
    <div class="home-link-entry-item-icon" :style="{'backgroundColor': item.bgColor}">
      <van-icon :name="item.icon"></van-icon>
    </div>
    <div>{{ item.text }}</div>
  </div>
</div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
      list: [
        { icon: 'renxiang', text: '整套', bgColor: '#44ce9b' },
        { icon: 'renshu', text: '单间', bgColor: '#ff5d6c' },
        { icon: 'icon-test', text: '品牌公寓', bgColor: '#00b1ed' },
        { icon: 'cunqianguan', text: '月付房租', bgColor: '#ffca28' }
      ]
    }
  }
}
</script>

<style lang="scss">
.home-link-entry {
  width: 100%;
  height: 100%;
  display: flex;
  font-size: 14px;
  &-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    &-icon {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      font-size: 30px;
      color: #fff;
      background: #ccc;
    }
  }
}
</style>

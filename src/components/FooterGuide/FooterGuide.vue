<template>
  <div class="footer_guide border-1px">
    <router-link
      href="javascript:;"
      class="guide_item"
      :to="{ path: '/msite' }"
      active-class="on"
    >
      <span class="item_icon">
        <i class="iconfont icon-waimai"></i>
      </span>
      <span>外卖</span>
    </router-link>
    <router-link
      href="javascript:;"
      class="guide_item"
      :to="{ path: '/search' }"
      active-class="on"
    >
      <span class="item_icon">
        <i class="iconfont icon-search">&#xe634;</i>
      </span>
      <span>搜索</span>
    </router-link>
    <router-link
      href="javascript:;"
      class="guide_item"
      :to="{ path: '/order' }"
      active-class="on"
    >
      <span class="item_icon">
        <i class="iconfont icon-dingdan">&#xe619;</i>
      </span>
      <span>订单</span>
    </router-link>
    <router-link
      href="javascript:;"
      class="guide_item"
      :to="{ path: '/profile' }"
      active-class="on"
    >
      <span class="item_icon">
        <i class="iconfont icon-geren">&#xe608;</i>
      </span>
      <span>我的</span>
    </router-link>
  </div>
</template>

<script>
export default {};
</script>

<style lang="stylus" scoped>
$green = #02a774;
$yellow = #F5A100;
$bc = #e4e4e4;

// 一像素下边框
bottom-border-1px($color) {
  position: relative;
  border: none;

  &:after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 1px;
    background-color: $color;
    transform: scaleY(0.5);
  }
}

// 一像素上边框
top-border-1px($color) {
  position: relative;

  &::before {
    content: '';
    position: absolute;
    z-index: 200;
    left: 0;
    top: 0;
    width: 100%;
    height: 1px;
    background-color: $color;
  }
}

// 根据像素比缩放1px像素边框
@media only screen and (-webkit-device-pixel-ratio: 2) {
  .border-1px {
    &::before {
      transform: scaleY(0.5);
    }
  }
}

@media only screen and (-webkit-device-pixel-ratio: 3) {
  .border-1px {
    &::before {
      transform: scaleY(0.333333);
    }
  }
}

// 根据像素比来使用 2x图 3x图
bg-image($url) {
  background-image: url($url + '@2x.png');

  @media (-webkit-min-device-pixel-ratio: 3), (min-device-pixel-ratio: 3) {
    background-image: url($url + '@3x.png');
  }
}

// 清除浮动
clearFix() {
  *zoom: 1;

  &::after {
    content: '';
    display: block;
    clear: both;
  }
}

.footer_guide {
  top-border-1px(#e4e4e4);
  position: fixed;
  z-index: 100;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #fff;
  width: 100%;
  height: 50px;
  display: flex;

  .guide_item {
    display: flex;
    flex: 1;
    text-align: center;
    flex-direction: column;
    align-items: center;
    margin: 5px;
    color: #999999;

    &.on {
      color: #02a774;
    }

    span {
      font-size: 12px;
      margin-top: 2px;
      margin-bottom: 2px;

      .iconfont {
        font-size: 22px;
      }
    }
  }
}
</style>
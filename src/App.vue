<template>
  <div>
    <transition name="router-fade" mode="out-in">
      <keep-alive>
        <router-view v-if="$route.meta.keepAlive"></router-view>
      </keep-alive>
    </transition>
    <transition name="router-fade" mode="out-in">
      <router-view v-if="!$route.meta.keepAlive"></router-view>
    </transition>
    <svg-icon></svg-icon>
  </div>
</template>

<script>
  import svgIcon from './components/common/svg';

  export default {
    components: {
      svgIcon
    },
  }

</script>

<!--注意下面样式没有添加scope，将作用与全局-->
<style lang="scss">
  @import './style/common';

  .router-fade-enter-active, .router-fade-leave-active {
    transition: opacity .3s;
  }

  .router-fade-enter, .router-fade-leave-active {
    opacity: 0;
  }

  /**修改h5中input的placeholder字体的颜色值*/
  input::-webkit-input-placeholder{
    color:#ccc;
  }
  input::-moz-placeholder{   /* Mozilla Firefox 19+ */
    color:#ccc;
  }
  input:-moz-placeholder{    /* Mozilla Firefox 4 to 18 */
    color:#ccc;
  }
  input:-ms-input-placeholder{  /* Internet Explorer 10-11 */
    color:#ccc;
  }
  /**修改h5中input的placeholder字体的颜色值*/
</style>

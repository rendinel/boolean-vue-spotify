<template>
  <div class="sidebar">

  </div>
</template>

<script>
export default {
  name: 'SideBar',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../public/style/positions.scss';
@import '../../public/style/color.scss';

.sidebar{
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 100px;
  background-color: $color-light;
}

</style>

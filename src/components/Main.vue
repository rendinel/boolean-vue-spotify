<template>
  <div class="main">

    <nav>
      <div class="left">
        <span class="material-icons">
          navigate_before
        </span>
        <span class="material-icons">
          navigate_next
        </span>
      </div>


        <div class="right">
          <span class="material-icons">
            account_circle
          </span>
          <span>John Doe</span>
          <span v-if="active === false" v-on:click="active = !active" class="material-icons">
          arrow_drop_down
          </span>
          <span v-if="active === true" v-on:click="active = !active" class="material-icons">
          arrow_drop_up
          </span>
        </div>

        <div class="dropdown" v-show="active">

        <div class="right-two" >

          <span>Account</span>

        </div>

        <div class="right-three">

          <span>Logout</span>

        </div>
        </div>
        




    </nav>

    <div class="square">1</div>
    <div class="square">2</div>
    <div class="square">3</div>
    <div class="square">4</div>
    <div class="square">5</div>
    <div class="square">6</div>
    <div class="square">7</div>
    <div class="square">8</div>
    <div class="square">9</div>
    <div class="square">10</div>
    <div class="square">11</div>
    <div class="square">12</div>
    <div class="square">13</div>
    <div class="square">14</div>
    <div class="square">15</div>

  </div>
</template>

<script>
export default {
  name: 'Main',
  props: {
    msg: String
  },
  data() {
    return{
      active:false,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../public/style/positions.scss';
@import '../../public/style/color.scss';

.main{
  position: fixed;
  top: 60px;
  left: 230px;
  background-color: red;
  width: calc(100% - 230px);
  height: calc(100% - 100px);
  overflow-y: auto;

  nav{
    position: fixed;
    top: 0;
    height: 60px;
    width: calc(100% - 230px);
    background-color: #101010;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    .left{
      width: 120px;
      height: 100%;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      span{
        background-color:$color-darkest;
        color: #fff;
        width: 28px;
        height: 28px;
        border-radius: 50%;
        @include col-c-c;
      }
      span:first-child{
        margin-right: 10px;
      }
    }
      .right{
      background-color: #232323;
      color: #fff;
      width: 200px;
      height: 40px;
      border-radius: 50px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      margin-right: 20px;
      padding: 0 35px 0 30px;
    }

    .dropdown{
      position: fixed;
      top: 55px;
      right: 0;

      .right-two{
      background-color: #232323;
      color: #fff;
      width: 200px;
      height: 40px;
      border-radius: 50px;
      display: flex;
      flex-direction: row;
      justify-content:center;
      align-items: center;
      margin-right: 20px;
      margin-bottom: 5px;
      padding: 0 35px 0 30px;
    }

    .right-three{
      background-color: #232323;
      color: #fff;
      width: 200px;
      height: 40px;
      border-radius: 50px;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-right: 20px;
      padding: 0 35px 0 30px;
    }
    }
    
  }

  .square{
    width: 100px;
    height: 100px;
    border: 1px solid green;
  }
}

</style>

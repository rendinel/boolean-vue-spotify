<template>
  <div class="sidebar">
    <img src="../assets/logo.svg" alt="">
    <div @click="setId = item.id" 
          class="icons-container" 
          :style="[setId === item.id ?  backChanged : '' ]" 
          v-for="item in sideIcons" :key="item.id">
      <span  class="material-icons icon">
        {{item.icons}}
      </span>
      <span class="txt">{{item.text}}</span>
    </div>

    <div class="play-container" v-for="item in playlist" :key="item.id">
      <span class="icon-two"><span :style="[item.id === 2 ?  iconBack : '' ]" class="material-icons">{{item.icons}}</span></span>
      <span class="txt-two">{{item.text}}</span>
    </div>

  </div>
</template>

<script>
const sideIcons = [
{
  id:"home",
  icons:"home",
  text:"Home"
},
{
  id:"search",
  icons:"search",
  text:"Search"
},
{
  id:3,
  icons:"leaderboard",
  text:"Your Library"
}
]

const playlist = [
{
  id:1,
  icons:"add",
  text:"Create Playlist"
},
{
  id:2,
  icons:"favorite",
  text:"Liked Songs"
}
]
export default {
  name: 'SideBar',
  props: {
    msg: String
  },
  data() {
    return {
      sideIcons,
      playlist,
      setId:"home",
      backChanged:{
        background:"#282828"
      },
      iconBack:{
        background:"linear-gradient(90deg, rgba(54,17,170,1) 0%, rgba(91,84,162,1) 43%, rgba(129,154,153,1) 100%)",
        color:"#B3B3B3"
      }
    }
  },
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../public/style/positions.scss';
@import '../../public/style/color.scss';

.sidebar{
  background-color: $color-darkest;
  width: 230px;
  height: 100%;
  div:nth-child(5){
    margin-top: 40px;
  }
  img{
    height: auto;
    width: 60%;
    margin: 20px 0 20px 20px;
  }
  .icons-container{
    width: 210px;
    height: 40px;
    border-radius: 5px;
    margin: 5px auto;
    display: flex;
    .icon{
      color: #B3B3B3;
      width: 55px ;
      height: 100%;
      @include col-c-c;
    }
    .txt{
      color:$color-lightest;
      @include col-c-c;
    }
  }
  .play-container{
    width: 210px;
    height: 40px;
    border-radius: 5px;
    margin: 5px auto;
    display: flex;
    // :hover{
    //   background-color: chartreuse;
    // }
    .icon-two{
      color: $color-darkest;
      width: 55px ;
      height: 100%;
      @include col-c-c;
      span:first-child{
        background-color: $color-lightest;
        width: 30px;
        height: 30px;
        @include col-c-c;       
      }
    }
    .txt-two{
      color:$color-lightest;
      @include col-c-c;
    }
  }
}

</style>

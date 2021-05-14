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

    <div class="main-nav">
      <div class="name-playlist">Recently Played</div>
      <div class="action">SEE ALL</div>
    </div>

    <div class="music-container">

      <div v-for="album in albums" :key="album.id" class="square">
        <img :src=" `${album.cover} ` " alt="">
        <div class="txt-container">
          <div class="group">{{album.title}}</div>
          <div class="album">{{album.subtitle}}</div>
        </div>
        <div class="play-hover">
          <i class="fas fa-play"></i>
        </div>
      </div>

    

    </div>

    <div class="main-nav">
      <div class="name-playlist">Favourites</div>
      <div class="action">SEE ALL</div>
    </div>

    <div class="music-container">

      <div v-for="album in albums" :key="album.id" class="square">
        <img :src=" `${album.cover} ` " alt="">
        <div class="txt-container">
          <div class="group">{{album.title}}</div>
          <div class="album">{{album.subtitle}}</div>
        </div>
        <div class="play-hover">
          <i class="fas fa-play"></i>
        </div>
      </div>

    

    </div>

  </div>
</template>

<script>
const albums = [
{
id:1,
cover:"https://images-na.ssl-images-amazon.com/images/I/51hbSVg115L._AC_SX466_.jpg",
title:"Motorhead",
subtitle:"Ace of Spades"
},
{
id:2,
cover:"https://images-na.ssl-images-amazon.com/images/I/51XyTOdXBnL._AC_SX425_.jpg",
title:"Metallica",
subtitle:"Master of Puppets"
},
{
id:3,
cover:"https://images-na.ssl-images-amazon.com/images/I/51O7k2hqS1L._AC_SY355_.jpg",
title:"Metallica",
subtitle:"Metallica"
},
{
id:4,
cover:"https://images-na.ssl-images-amazon.com/images/I/51fnmTjALvL._AC_SY450_.jpg",
title:"Lamb of God",
subtitle:"Ashes of the Wake"
},
{
id:5,
cover:"https://images-na.ssl-images-amazon.com/images/I/81iabVrElHL._AC_SX522_.jpg",
title:"Pantera",
subtitle:"Far Beyond Driven"
},
{
id:6,
cover:"https://images-na.ssl-images-amazon.com/images/I/61CfTX9vIHL._AC_SX522_.jpg",
title:"Overkill",
subtitle:"Feel the fire"
},
{
id:7,
cover:"https://www.rollingstone.com/wp-content/uploads/2020/02/masterofreality.jpg",
title:"Black Sabbath",
subtitle:"Masters of Reality"
},
{
id:8,
cover:"https://images-na.ssl-images-amazon.com/images/I/51hXXepLspL._AC_SY355_.jpg",
title:"Black Label Society",
subtitle:"Sonic Brew"
},
{
id:9,
cover:"https://images-na.ssl-images-amazon.com/images/I/51PMG0CJ1HL._AC_SY355_.jpg",
title:"Black Label Society",
subtitle:"Mafia"
}

]
export default {
  name: 'Main',
  props: {
    msg: String
  },
  data() {
    return{
      active:false,
      albums
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
  background-color: $color-dark;
  width: calc(100% - 230px);
  height: calc(100% - 100px);
  overflow-y: auto;

  nav{
    position: fixed;
    top: 0;
    height: 60px;
    width: calc(100% - 230px);
    background-color: $background-card;
    @include row-sp-c;
    .left{
      width: 120px;
      height: 100%;
      @include row-c-c;
      span{
        background-color:$color-darkest;
        color: $color-white;
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
      background-color: $color-light;
      color: $color-white;
      width: 200px;
      height: 40px;
      border-radius: 50px;
      @include row-sp-c;
      margin-right: 20px;
      padding: 0 35px 0 30px;
    }

    .right:hover{
      cursor: default;
    }

    .dropdown{
      position: fixed;
      top: 55px;
      right: 0;
      background-color: $color-light;
      width: 200px;
      height: 80px;
      margin-right: 20px;
      border-radius: 10px;
      z-index: 1000;

      .right-two,.right-three{
      color: $color-white;
      width: 200px;
      height: 40px;
      @include row-c-c;
      padding: 0 35px 0 30px;
      z-index: 1000;
    }
    .right-two{
      border-bottom: 0.5px solid gray;
    }
    }
    
  }

  .main-nav {
    width: calc(100% - 50px);
    margin: 0 auto;
    height: 50px;
    @include row-sp-c;
   .name-playlist{
      color:$color-white;
      font-size: 25px;
    }
     .action{
       color: $color-lightest;
       font-size: 15px;
     }
  }

  .music-container{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    .square{
    width: 210px;
    height: 295px;
    border-radius: 5px;
    background-color: $background-card;
    @include col-c;
    margin-left: 25px;
    margin-bottom: 25px;
    position: relative;
    z-index: -5;
    &:hover{
      background-color:$color-light ;
    }
    &:hover .play-hover{
      opacity: 1;
    }
    .play-hover{
      position: absolute;
      top: 140px;
      right: 30px;
      background-color: $color-green;
      height: 40px;
      width: 40px;
      border-radius: 50%;
      opacity: 0;
      @include col-c-c;
      i{
        color: $color-white;
      }
    }
    img{
      width: 168px;
      height: 168px;
      margin-top: 20px;
    }
    .txt-container{
      @include col;
      width: 80%;
      .group{
      margin: 30px 0 15px 0;
      color: $color-white;
    }
    .album{
      color: $color-lightest;
    }
    }
  }
  }
}

</style>

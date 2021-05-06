<template>
  <div class="playbar">

      <footer>
        <div class="mini">

            <div class="img-player-left"> <img  src="../assets/sinister.jpeg" alt=""> </div>
            <div class="mini-txt">
              <h5 class="txt-wh">Sinister</h5>
              <div class="txt-gr">Brano Nome</div>
            </div>

            <div>
              <i class="mini-fa fa fa-folder-o" aria-hidden="true"></i>
              <i class="mini-fa fa fa-heart-o" aria-hidden="true"></i>
            </div>

        </div>
        <div class="player">
            <div class="player-control-bar">
              <ul>
                <li><i class="fa fa-random"></i></li>
                <li><i class="fa fa-step-backward" aria-hidden="true"></i></li>
                <li class="big"><i class="fa fa-play-circle-o" aria-hidden="true"></i></li>
                <li><i class="fa fa-step-forward" aria-hidden="true"></i></li>
                <li><i class="fa fa-repeat" aria-hidden="true"></i></li>
              </ul>
            </div>
            <div class="player-control-time">
              <div class="elapsed-time perc-20">
                <div class="point"></div>
              </div>
            </div>
        </div>

        <div class="options">
          <div>
            <i class=" option-fa fa fa-bars" aria-hidden="true"></i>
            <i class=" option-fa fa fa-desktop" aria-hidden="true"></i>
            <i class="option-fa fa fa-volume-up" aria-hidden="true"></i>
          </div>
          <!-- <div class="hr-volume"></div> -->
          <div class="player-control-time-two">
            <div class="elapsed-time perc-20">
              <div class="point"></div>
            </div>
          </div>
        </div>
      </footer>

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

.playbar{
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 100px;
  background-color: $color-light;
}

footer {
  height: 90px;
  background: #282828;
  display: flex;
  justify-content: space-between;
  color: #fff;
}

.mini, .options {
  width: 20%;
}

.img-player-left{
  width: 20%;
}

.img-player-left > img{
  width: 100%;
}

.mini{
  justify-content: space-around;
  align-items: center;
  display: flex;
}

.options{
  justify-content: space-around;
  align-items: center;
  display: flex;
}

.option-fa{
  margin-right: 15px;
}

.mini-fa{
  margin-right: 15px;
}

.hr-volume{
  background-color: #717171;
  width: 120px;
  height: 4px;
}

.player {
  width: 60%;
  text-align: center;
}

.player ul {
  display: flex;
  justify-content: center;
  align-items: center;
}

.player ul li {
  list-style: none;
  font-size: 16px;
  padding: 10px;
}

.player ul li.big {
  font-size: 32px;
  padding: 10px 20px;
}

.player ul li.big:hover {
  transform: scale(1.2);
}

.player-control-time {
  background: rgba(255,255,255,.2);
  width: 100%;
  height: 4px;
}

.player-control-time .elapsed-time {
  position: relative;
  background: rgba(255,255,255,.8);
  height: 100%;
}

.elapsed-time .point {
  display: none;
  position: absolute;
  width: 15px;
  height: 15px;
  background-color: #fff;
  border-radius: 50%;
  transform: translate(50%, -50%);
  right: 0;
  top: 50%;
}

.player-control-time:hover .point {
  display: block;
}

.perc-20 {
  width: 20%;
}

.perc-40 {
  width: 40%;
}

.player-control-time-two {
  background: rgba(255,255,255,.2);
  width: 120px;
  height: 4px;
}

.player-control-time-two .elapsed-time {
  position: relative;
  background: rgba(255,255,255,.8);
  height: 100%;
}

.elapsed-time .point {
  display: none;
  position: absolute;
  width: 15px;
  height: 15px;
  background-color: #fff;
  border-radius: 50%;
  transform: translate(50%, -50%);
  right: 0;
  top: 50%;
}

.player-control-time-two:hover .point {
  display: block;
}

.perc-20 {
  width: 20%;
}

.perc-40 {
  width: 40%;
}



</style>

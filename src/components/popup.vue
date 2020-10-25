<template>
  <div class="popup">
    <transition name="fade">
        <div class="popup-mask" v-if="isShow" @click="closepopup"></div>
    </transition>
      <transition name="popup-drop">
      <div class="popup-content" v-if="isShow" >
        <div class="popup-close" @click="closepopup">
          <img src="../../src/assets/images/close.png" alt="">
        </div>
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props:{
    isShow:{
      type: Boolean,
      default:false
    }
  },
  data () {
    return {
      msg: ''
    }
  },
  methods: {
    closepopup() {
      this.$emit("close")
    }
  }
}
</script>

<style lang="scss">
.popup{
    // width: 100%;
    // height: 100%;
    .popup-mask{
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        width: 100%;
        height: 100%;
        z-index: 100;
        background-color: #000;
        opacity: 0.3;
    }
    .popup-content{
      position: absolute;
      top: 30%;
      left: 50%;
      margin-left: -25%;
      overflow: hidden;
      width: 50%;
      max-height: 50%;
      z-index: 200;
      box-shadow: 7px 7px 10px 0 rgba(76, 110, 245, .1);
      border-radius: 5px;
      padding: 30px;
      background-color: #fff;
      .popup-close{
          position: absolute;
          top: 10px;
          right: 10px;
          width: 20px;
          height: 20px;
          text-align: center;
          cursor: pointer;
          z-index: 200;
          img{
            width: 100%;
            height: 100%;
            }
          &:hover {
            img {
              transform: scale(1.5, 1.5);
        }
      }
      }
    }
}
</style>

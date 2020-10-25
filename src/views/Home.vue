<template>
  <div class="home">
        <popup :isShow="isShow" @close="close()">
          <div v-for="item in 10" :key="item">和我一起看富爸爸穷爸爸吧{{item}}</div>
        </popup>
        <div class="btn" @click="downorclose()">点我开启/关闭</div>
  </div>
</template>

<script>
import popup from '@/components/popup.vue'
export default {
  name: 'Home',
  components: {
    popup
  },
  data() {
    return {
      isShow:false
    }
  },
  methods:{
    close() {
      this.isShow = false
    },
    downorclose() {
      this.isShow = !this.isShow
    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  .btn{
    width: 200px;
    height: 200px;
    background-color: red;
  }
}
</style>


<template>
  <div><i-tabs :current="current_scroll" scroll @change="handleChangeScroll">
    <i-tab key="tab1" title="选项1"></i-tab>
    <i-tab key="tab2" title="选项2"></i-tab>
    <i-tab key="tab3" title="选项3"></i-tab>
    <i-tab key="tab4" title="选项4"></i-tab>
    <i-tab key="tab5" title="选项5"></i-tab>
    <i-tab key="tab6" title="选项6"></i-tab>
    <i-tab key="tab7" title="选项7"></i-tab>
    <i-tab key="tab8" title="选项8"></i-tab>
    <i-tab key="tab9" title="选项9"></i-tab>
</i-tabs>
      <view class="top-padding">
      <i-card title="良品铺子" extra="零食" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">好多不错的零食</view>
        <view slot="footer">后街1-22</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
      <i-card title="卡片标题" i-class="top-padding" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <view class="top-padding"></view>
    </view>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      current_scroll: 'tab1',
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },

  components: {
    card
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    handleChange ({ detail }) {
        this.setData({
            current: detail.key
        });
    },
    handleChangeScroll (event) {
        this.current_scroll = event.mp.detail.key
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
.top-padding {
  padding-top: 50rpx;
}
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
</style>

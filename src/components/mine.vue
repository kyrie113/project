<template>
<div>
    <div class="mine"> 
        <van-row class="mine_top">
  <van-col span="4" class="mine_top_left"><van-icon name="volume-o"  size="25px"/></van-col>
  <van-col span="16">我的</van-col>
  <van-col span="4"><van-icon name="setting-o" info="9" size="25px"/></van-col>
</van-row>  
    </div>
    <van-pull-refresh v-model="isLoading" @refresh="onRefresh">
    <div class="user_info">
        <van-row>
            <van-col span="4" offset="1" ><img src="static/user/userIcon.png" alt=""></van-col>
            <van-col offset="1"> <span class="user_info_name">用户 {{ count }}<br></span>
            <van-row class="user_info_phone"> 21354654</van-row>
            </van-col>
        
        </van-row>
    </div>
    <div class="user_data">
      <van-row class="detail">
        <van-col span="8" class="money">1 <span class="money_style">元&nbsp</span>
        <van-row class="detail_text"> 钱包 </van-row> </van-col>
        <van-col span="8" class="discount">5<span class="discount_style">个&nbsp</span> 
        <van-row class="detail_text"> 优惠 </van-row>  </van-col>
        <van-col span="8" class="gold">6<span class="gold_style">个&nbsp</span>
        <van-row class="detail_text"> 金币 </van-row>  </van-col>
      </van-row>
    </div>
    <div class="banner">
        <img src="static/user/timg.jpg" alt="">
    </div>
</van-pull-refresh>

    </div>
</template>
<script>
export default {
  data() {
    return {
      count: 0,
      isLoading: false,
    }
  },

  methods: {
    onRefresh() {
      setTimeout(() => {
        this.$toast('刷新成功');
        this.isLoading = false;
        this.count++;
      }, 500);
    }
  }
}
</script>
<style lang="less" scoped>
 .mine{
     font-size: 25px;
     background-color: rgba(0, 191, 255);
     padding-top:20px;
     height: 50px;
     text-align: center;
    &_top{
        &_left{
            
        }
    }
 }
.user_info{
    padding-top: 10px; 
    &_name{
      font-size: 25px;

    }
    &_phonenumber{
    
          }
}
.user_data{
  .detail{
    text-align: center;
     font-weight: bold;
     &_text{
       font-size:15px;
     }
  }
  .money{
    font-size: 20px;
    color: blue;
    &_style{
      font-size: 10px;
    }
  }
  .discount{
    font-size: 20px;
    color: red;
    &_style{
      font-size: 10px;
    }
  }
  .gold{
    font-size: 20px;
    color: orange;
    &_style{
      font-size: 10px;
    }
  }
}
.banner{
  height: 100px;
}

</style>

<template>
    <div class="datas" id="vueContent">
      <div class="top">
        <div class="inner">
          <div class="left">
            <div class="title data_icon">统计数据</div>
          </div>
        </div>
      </div>
      <div class="view">
        <div class="innerView">
          <div class="counts viewItem">
            <div class="viewTop clearfix">
              <div class="topL fl">生病人数统计</div>
              <div class="topR fr">
                <div class="time fl">
                  <span>时间：</span>
                  <a href="javascript:;" class="btn-time active">7天</a>
                  <a href="javascript:;" class="btn-time">14天</a>
                  <a href="javascript:;" class="btn-time">30天</a>
                </div>
                <div class="date fl">
                  <span>日期：</span>
                  <el-date-picker
                    v-model="startDate"
                    type="date"
                    placeholder="选择日期">
                  </el-date-picker>
                  <span class="line"> - </span>
                  <el-date-picker
                    v-model="endDate"
                    type="date"
                    placeholder="选择日期">
                  </el-date-picker>
                </div>
              </div>
            </div>
            <div class="viewDatas">
              <ul class="clearfix">
                <li>
                  <div class="img"><img src="../../assets/images/img_icon_jz.png" alt=""></div>
                  <div class="data">
                    <div class="count jz"><span>12</span>人</div>
                    <div class="text">就诊总数<i class="up"></i></div>
                  </div>
                </li>
                <li>
                  <div class="img"><img src="../../assets/images/img_icon_pt.png" alt=""></div>
                  <div class="data">
                    <div class="count pt"><span>12</span>人</div>
                    <div class="text">普通疾病<i class="up"></i></div>
                  </div>
                </li>
                <li>
                  <div class="img"><img src="../../assets/images/img_icon_gm.png" alt=""></div>
                  <div class="data">
                    <div class="count gm"><span>12</span>人</div>
                    <div class="text">感冒发烧<i class="up"></i></div>
                  </div>
                </li>
                <li>
                  <div class="img"><img src="../../assets/images/img_icon_bd.png" alt=""></div>
                  <div class="data">
                    <div class="count bd"><span>12</span>人</div>
                    <div class="text">传染病<i class="down"></i></div>
                  </div>
                </li>
              </ul>
            </div>
          </div>
          <div class="dataChange viewItem">
            <div class="viewTop clearfix">
              <div class="topL fl">生病就诊数据变化</div>
              <div class="topR fr">
                <div class="time fl">
                  <span>时间：</span>
                  <a href="javascript:;" class="btn-time active">昨日</a>
                  <a href="javascript:;" class="btn-time">今日</a>
                  <a href="javascript:;" class="btn-time">最近7日</a>
                </div>
                <div class="date fl">
                  <span>日期：</span>
                  <el-date-picker
                    v-model="value"
                    type="date"
                    placeholder="选择日期">
                  </el-date-picker>
                </div>
              </div>
            </div>
            <div class="viewDatas">

            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    name: 'Index',
    data(){
      return {
        startDate: '',
        endDate: '',
        value:''
      }
    }
  }
</script>

<style scoped lang="less">
  .view{
    padding:22px 52px;
    box-sizing: border-box;
    .innerView{
      max-width: 1140px;
      .viewItem{
        margin-bottom: 25px;
        box-shadow: 0px 0px 5px 0px rgba(171, 171, 171, 0.42);
        background: #fff;
        border-radius: 4px;
        .viewTop{
          padding:15px 22px;
          /*height: 60px;*/
          /*line-height: 60px;*/
          box-sizing: border-box;
          border-bottom: 1px solid #f1f1f1;
          .topL{
            padding:0 16px;
            position: relative;
            line-height: 30px;
            &:before{
              content: '';
              width: 4px;
              height: 20px;
              background: #06a3e2;
              font-size: 16px;
              color: #333333;
              position: absolute;
              left: 0;
              top:50%;
              transform: translateY(-50%);
              border-radius: 20px;
            }
          }
          .topR{
            font-size: 14px;
            .time{
              line-height: 30px;
              margin-right: 60px;
              .btn-time{
                padding:2px 12px;
                color: #292929;
                &.active{
                  background: #06a3e2;
                  border-radius: 40px;
                  color: #fff;
                }
              }
            }
            .line{
              color: #d8d8d8;
            }
          }
        }
      }
      .counts{
        .viewDatas{
          padding:28px 0 52px;
          ul{
            li{
              float: left;
              width: 25%;
              text-align: center;
              font-size: 0;
              box-sizing: border-box;
              + li{
                border-left: 1px solid #efefef;
              }
              .img{
                width: 79px;
                height: 79px;
                display: inline-block;
                vertical-align: middle;
                margin-right: 20px;
                img{
                  width: 100%;
                  height: 100%;
                }

              }
              .data{
                display: inline-block;
                vertical-align: middle;
                text-align: left;
                .count{
                  font-size: 22px;
                  margin-bottom: 10px;
                  span{
                    font-size: 36px;
                  }
                  &.jz{
                    color: #009af0;
                  }
                  &.pt{
                    color: #5ac8c9;
                  }
                  &.gm{
                    color: #ffcb27;
                  }
                  &.bd{
                    color: #ff6767;
                  }
                }
                .text{
                  font-size: 15px;
                  color: #4a4a4a;
                  i{
                    display: inline-block;
                    width: 19px;
                    height: 20px;
                    margin-top: -3px;
                    vertical-align: middle;
                    margin-left: 12px;
                    &.up{
                      background: url("../../assets/images/img_up.png") no-repeat;
                      background-size: 100% 100%;
                    }
                    &.down{
                      background: url("../../assets/images/img_down.png") no-repeat;
                      background-size: 100% 100%;
                    }
                  }
                }
              }
            }
          }
        }
      }
      .dataChange{
        .viewDatas{
          width: 100%;
          height: 350px;
        }
      }

    }
  }


  /deep/ .el-date-editor.el-input{
    width: 140px;
    .el-input__inner{
      height: 30px;
      line-height: 30px;
    }
    .el-input__icon{
      line-height: 30px;
    }
  }
</style>

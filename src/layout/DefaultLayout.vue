<template>
  <div class="home">
    <el-row class="head">
      <el-col :span="4">
        <div class="flex align-end">
          <el-button type="text" @click="() => {if(windowWidth >= 720) isCollapse = !isCollapse}"><img src="../assets/icon/hamber.svg" width="20px"/></el-button>
          <img  src="../assets/Lgog.png" :width="windowWidth > 720 ? '164px' : '90px'" class="logo" alt="">
        </div>
      </el-col>
      <el-col :span="20">
        <div class="flex " :class="{'justify-between': windowWidth > 1355,'justify-end': windowWidth <= 1355 }" style="height:50px">
          <div class="flex" v-if="windowWidth > 1355">
            <el-input placeholder="Search here..." v-model="searchInput" class="input-with-select">
             <img :src="searchIcon" slot="append" width="18px" style="margin-top: 3px; cursor: pointer;"/>
           </el-input>
           <el-select v-model="selectBy" placeholder="select" class="select">
             <el-option
               v-for="item in options"
               :key="item.value"
               :label="item.label"
               :value="item.value">
             </el-option>
           </el-select>
          </div>
          <div class="flex justify-between" :class="{'w-40': windowWidth > 1355 }">
            <div class="flex" v-if="windowWidth > 695">
              <div class="flex weather" >
                <img :src="weatherIcon"/>
                <span>09:54 am</span>
              </div>
              <el-select v-model="place" placeholder="select" class="select citySelect">
                 <el-option
                   v-for="item in cityOptions"
                   :key="item.value"
                   :label="item.label"
                   :value="item.value">
                 </el-option>
               </el-select>
            </div>
            <div class="flex">
              <img :src="settingIcon" width="25px" style="cursor: pointer;"/>
              <img :src="ringIcon" width="22px" style="cursor: pointer" :style="{'margin-left': windowWidth > 695 ? '40px' : '10px', 'margin-right': windowWidth > 695  ? '0px': '20px'  }"/>
            </div>
            <div class="flex avatar">
              <img :src="userImg" class="user"/>
              <img :src="arrowIcon" width="12px"/>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
    <el-row class="tac">
    <el-col :span="24">
      <div class="flex">
        <LeftNavigation :isCollapse="isCollapse"/>
        <router-view/>
      </div>
    </el-col>
  </el-row>
  <WindowResizeListener @resize="handleResize"/>
  </div>
</template>

<script>
import LeftNavigation from '@/components/LeftNavigation.vue';
import searchIcon from '../assets/icon/search.svg'
import weatherIcon from '../assets/icon/weather.svg'
import settingIcon from '../assets/icon/setting.svg'
import ringIcon from '../assets/icon/ring.svg'
import userImg from '../assets/avatar.png'
import arrowIcon from '../assets/icon/arrow.svg'
import WindowResizeListener from '@/components/WindowResizeListener.vue'
export default {
  components: {
    LeftNavigation,
    WindowResizeListener
  },
  data () {
    return {
      isCollapse: false,
      searchIcon,
      weatherIcon,
      settingIcon,
      ringIcon,
      userImg,
      arrowIcon,
      windowWidth: '',
      searchInput: '',
      selectBy: 'all',
      place: 'Antananarivo',
      options: [
        {label: 'By All', value: 'all'},
        {label: 'By Station', value: 'Station'},
        {label: 'By Country', value: 'Country'},
      ],
      cityOptions: [
        {label: 'Antananarivo', value: 'Antananarivo'},
        {label: 'Hongkong', value: 'Hongkong'},
        {label: 'Taipei', value: 'Taipei'},
        {label: 'Tokyo', value: 'Tokyo'},
      ]
    }
  },
  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth
      if (window.innerWidth <= 695) {
        this.isCollapse = true
      }
    },
  },
  created() {
    this.handleResize()
  }
}
</script>

<style scoped>

.head {
  padding: 38px 20px;
}
.logo {
  height: 35px;
  margin-left: 20px
}
@media (max-width: 720px) {
  .head {
    padding: 20px;
    padding-bottom: 0px
  }
  .logo {
    height: auto;
  }
}
.select {
  width: 101px;
  margin-left:10px;
  font-size: 18px!important;
}
.weather {
  align-items: center;
}
.weather img {
  width: 25px;
  margin-right: 8px
}
.weather span {
  font-size: 18px;
  color: #374557;
  font-weight: 600;
}
.citySelect {
  width: 140px;
  margin-top: 4px
}

.avatar .user {
  margin-right:5px;
  cursor: pointer;
}
/deep/ .el-input-group--append {
  border-color: #737791;
  border-width: 2px;
  font-size: 18px;
  width: 245px;
}
/deep/ .el-input-group__append {
  background-color: #fff;
  padding: 0px 10px;
  border-color: #737791;
  position: relative;
}
/deep/ .el-input-group__append::after {
  content: '';
  position: absolute;
  width: 1px;
  height: 24px;
  background: #000;
  left: 0px;
}
.input-with-select /deep/ .el-input__inner {
  border: 1px solid #737791;
  border-right: 0px;
  height: 50px
}
/deep/ .el-input__inner:focus {
  border-color: #737791;
}
.select /deep/ .el-input__inner{
  border-right: 1px;
  border: 1px solid #737791;
  border-color: #737791!important;
  height: 50px;
}
.citySelect /deep/ .el-input__inner{
  border: none;
  background: #F5F5F5;
  font-size: 18px;
  padding: 0px
}
</style>

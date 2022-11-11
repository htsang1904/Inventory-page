<template>
  <div id="app">
    <el-row>
      <el-col :span="17" id="main">
        <el-container style="height: 744px;">       
            <el-header style="text-align: center; margin-top: 10px;">
              <el-row :gutter="10">
                <el-col  :span="1"><i class="el-icon-back"></i></el-col>
                <el-col  :span="4"><span class="title">Kiểm kho</span></el-col>
                <el-col :span="11">
                  <el-input
                    placeholder="Tìm hàng hóa theo mã hoặc tên"
                    prefix-icon="el-icon-search"
                    suffix-icon="el-icon-more"
                    border
                    v-model="search">
                  </el-input>
                </el-col>
              <el-col  :span="8">         
                <el-row>
                  <el-button type="primary" icon="el-icon-edit"></el-button>
                  <el-button type="primary" icon="el-icon-share"></el-button>
                  <el-button type="primary" icon="el-icon-delete"></el-button>
                  <el-button type="primary">Upload<i class="el-icon-upload"></i></el-button>
                </el-row>
              </el-col>
        </el-row>
            </el-header>
            <MainInventoryVue/>
        </el-container>
      </el-col>
      <el-col :span="7" id="aside">
        <AsideInventoryVue/> 
      </el-col>
  </el-row>
  </div>
</template>

<script>
import MainInventoryVue from './components/MainInventory.vue';
import AsideInventoryVue from './components/AsideInventory.vue';

export default { 
  components: {
    MainInventoryVue,
    AsideInventoryVue,
  },
  data() {
    return {
      search: ''
    }
  } 
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrat', sans-serif !important;
}
@media (max-width: 820px) {
  #app > .el-row {
    display: flex;
    flex-direction: column;
  }
  #app > .el-row > #main, 
  #app > .el-row > #aside {
    width: 100%;
  }
  .el-header > {
      .el-row > {
        :nth-child(4) {
            display: none;
        }
      }
  }
}
#app {
  background-color: #DCDFE6; 
  width: 100%;
}
  #app .el-header {
    background-color: #DCDFE6;
    color: #333;
    line-height: 60px;
  }

  #app .el-header .el-row {
    .el-icon-back, .title {
      font-size: 24px;
      font-weight: bold;
    }
    :nth-child(4) {
      position: relative;
      .el-row {
        position: absolute;
        right: -5px;
        bottom: -60px;
        .el-button {
          background-color: #607B8B;
          border-color: #DCDFE6;
          height: 50px;
        }
        :hover {
            opacity: 0.5;
          }    
      }
    }
  }
  input.el-input__inner {
    height: 50px;
}
  
</style>

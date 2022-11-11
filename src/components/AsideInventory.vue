<template>
        <el-aside width="" style="background-color: white; margin: 10px; padding: 10px;">
        <el-row type="flex" justify="space-between">
            <el-col :span="12">
                <el-avatar shape="square" :size="50" :src="avatar"></el-avatar>
                <span> GuTa Việt Nam</span>
            </el-col>
            <el-col :span="12">07/11/2022 15:43</el-col>
        </el-row>
        <el-row type="flex" justify="space-between">
            <el-col :span="12">Mã kiểm kho</el-col>
            <el-col :span="12">
                <el-input placeholder="Nhập mã kho" v-model="maKho"></el-input>
            </el-col>
        </el-row>
        <el-row type="flex" justify="space-between">
            <el-col :span="12">Trạng thái</el-col>
            <el-col :span="12">Phiếu tạm</el-col>
        </el-row>
        <el-row type="flex" justify="space-between">
            <el-col :span="12">Tổng số lượng thực tế</el-col>
            <el-col :span="12">10</el-col>
        </el-row>
        <el-input
                type="textarea"
                :autosize="{ minRows: 2, maxRows: 4}"
                placeholder="Ghi chú..."
                v-model="note">
        </el-input>
        <el-container style="border: 1px solid #DCDFE6; margin-top: 10px; height: 340px;">
            <el-header style="background-color: #607B8B; height: 30px; line-height: 30px; font-weight: bold; color: white">
                Kiểm gần đây
            </el-header>
            <el-col>
                <div v-for="(item,index) in listItem" :key="index">
                    <span>{{}}</span>
                </div>
            </el-col>
        </el-container>
            <el-row :gutter="20">
                <el-col :span="12">
                    <el-button type="primary">Lưu <i class="el-icon-files"></i></el-button>
                </el-col>
                <el-col :span="12">
                    <el-button @click="done" type="success">Hoàn Thành <i class="el-icon-check"></i></el-button>
                </el-col>
            </el-row>
        </el-aside>
</template>

<script>

export default {
    data() {
        return {
            avatar: 'https://scontent.fsgn3-1.fna.fbcdn.net/v/t1.6435-9/119312336_1006014389836846_8401732968803933021_n.png?_nc_cat=104&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=WC4I9KFhrwUAX_J2ngX&_nc_ht=scontent.fsgn3-1.fna&oh=00_AfD5bR4DmBIwVsMuMTYNzFgsDWSUAufq84SpN_P_1Wgl0w&oe=63902BDE',
            maKho: '',
            note: '',
            listItem: []
        }
    },
    methods: {
        done() {
        this.$message({
          type: 'success',
          message: 'Hoàn Thành'
        })
      }
    }
}
</script>

<style lang="scss">
.el-avatar {
    margin-right: 10px;
}
.el-col-12 {
    display: flex;
    height: 60px;
    align-items: center;
    width: 41.66667%;
    text-align: center;
    font-size: 14px;
}
.el-aside {
    :nth-child(1) {
            :nth-child(2){
                justify-content: right;
            }
    }
    
}
.el-aside {
    :nth-child(1), :nth-child(2), :nth-child(3), :nth-child(4) {
            :nth-child(1) {
                font-weight: 800;
            }
    }
    :nth-child(6) {
        border-radius: 10px;
        .el-header {
            border-radius: 10px 10px 0 0;
        }
    }
   
}
.el-aside .el-button {
    margin-top: 10px;
    width: 100%;
    height: 50px;
}
</style>
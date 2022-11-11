<template>
        <el-main style="padding: 0; height: 100%; margin: 10px;">
        <el-table :data="tableData"
                border
                height="100%"
                style="width: 100%; font-weight: bold;">
          <el-table-column prop="stt" label="Stt" width="60">
          </el-table-column>
          <el-table-column prop="maHang" label="Mã hàng" width="160">
          </el-table-column>
          <el-table-column prop="tenHang" label="Tên hàng" width="280">
          </el-table-column>
          <el-table-column prop="dvt" label="ĐVT" width="160">
          </el-table-column>
          <el-table-column prop="tonKho" label="Tồn" width="100">
          </el-table-column>
          <el-table-column prop="thucTe" label="Thực tế" width="100">
          </el-table-column>
          <el-table-column label="Tùy chỉnh" width="180">
              <el-button size="medium">Sửa</el-button>
              <el-button @click="deleteItem" size="medium" type="danger" >Xóa</el-button>
          </el-table-column>
        </el-table>
      </el-main>
</template>
<script>
export default {
    data() {
      const item = {
        stt: '1',
        maHang: 'NVT 146',
        tenHang: 'Sữa ông thọ',
        dvt: 'Thùng',
        tonKho: '0',
        thucTe: '0',
        slLech: '0',
        giaTriLech: '0'
      };
       
      return {
        tableData: Array(30).fill(item),
      }
    },
    methods: {
      deleteItem() {
        this.$confirm('Bạn có chắc chắn xóa mặt hàng này','Thông báo',{
          confirmButtonText: 'Xóa',
          cancelButtonText: 'Hủy',
          type: 'warning'
        }).then(() => {
          this.$message({
            type: 'success',
            message: 'Xóa thành công'
          });
        }).catch(() => {
          this.$message({
            type: 'info',
            message: 'Hủy xóa'
          });
        });
      },
    }
}
</script>
<style lang="scss">
.el-main .el-table thead {
    font-weight: bold;
    font-size: 16px;
    justify-items: center;
    color: black;  
}

.cell {
    text-align: center;
}

table.el-table__body {
    font-weight: 400;
    color: black;
}
</style>
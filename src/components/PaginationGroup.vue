<template>
  <div class="flex pagination align-end">
    <p class="total">Total 480 |</p>
    <i @click="() => {if(value < 10)value ++}" class="el-icon-arrow-left el-icon--left"/>
    <el-select v-model="value" class="select">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
      </el-option>
    </el-select>
    <i @click="() => { if(value > 1)value-- }" class="el-icon-arrow-right el-icon--right"/>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        value: 1,
        options: [
          { value: 1,label: 1},
          { value: 2, label: 2 },
          { value: 3, label: 3 },
          { value: 4, label: 4 },
          { value: 5, label: 5 },
          { value: 6, label: 6 },
          { value: 7, label: 7 },
          { value: 8, label: 8 },
          { value: 9, label: 9 },
          { value: 10, label: 10 },
        ]
      }
    }
  }
</script>

<style scoped>
.total {
  color: #737791;
  font-size: 16px;
  line-height: 0;
  font-weight: 600;
  margin-right: 15px
}
i {
  cursor: pointer;
  font-weight: 700;
}
.select /deep/ .el-input__inner {
  border: 0px;
  width: 60px;
}
</style>
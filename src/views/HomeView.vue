<template>
  <div class="home">
    <div class="flex breadcrumb">
      <el-breadcrumb separator-class="el-icon-arrow-right">
        <el-breadcrumb-item >home</el-breadcrumb-item>
        <el-breadcrumb-item>My Collection</el-breadcrumb-item>
      </el-breadcrumb>
    </div>
    <div class="flex filter">
      <InputGroup title="Category">
        <el-select v-model="selectBy" placeholder="Select">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
      </InputGroup>
      <InputGroup title="Subtitle">
        <el-input v-model="subtitle" placeholder=""></el-input>
      </InputGroup>
      <InputGroup title="">
        <el-button class="search">Search</el-button>
      </InputGroup>
    </div>
    <div class="collection">
      <div class="flex justify-between align-end">
        <h2>My Collection</h2>
        <PaginationGroup/>
      </div>
      <div>
        <CollectionItem v-for="item in 6" :key="item"/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import InputGroup from '@/components/inputGroup.vue'
import PaginationGroup from '@/components/PaginationGroup.vue'
import CollectionItem from '@/components/CollectionItem.vue'
export default {
  name: 'HomeView',
  components: {
    InputGroup,
    PaginationGroup,
    CollectionItem
  },
  data() {
    return {
      subtitle: '',
      selectBy: 'HR Announcement',
      options: [{
        value: 'HR Announcement',
        label: 'HR Announcement'
      }, {
        value: 'News',
        label: 'News'
      }, {
        value: 'All',
        label: 'All'
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  padding-right: 20px;
}
.breadcrumb {
  padding: 20px 10px;
}
.filter {
  height:124px;
  padding: 20px ;
  padding-top:0px;
  background-color: #fff;
  display: flex;
  align-items: center;
}
.filter > div { margin-right: 12px;}
.search {
  background: #F2F2F7;
  color:#32395F;
  border: 0px;
  font-size: 18px;
  margin-top:15px
}
.collection {
  margin-top: 30px;
  h2 {
    color: #11263C;
    font-size: 16px;
  }
}
</style>

<template>
  <div class="data-integrate">
    <div class="nav">
      <el-collapse accordion>
        <el-collapse-item :title="item.name" name="1" v-for="(item,index) in dataList" :key="index" v-show="pathName == item.routeName">
          <div @click="handleChangeData(items.routeName)" v-for="(items,index) in item.child" :key="index">{{items.name}}</div>
        </el-collapse-item>
      </el-collapse>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return {
      pathName:'data-integrate',
      dataList:[
        {
          name:'数据一',
          routeName:'data-integrate',
          child:[
            {
              name:'数据一',
              routeName:'data-one'
            }
          ]
        },
        {
          name:'数据二',
          routeName:'data-extract',
          child:[
            {
              name:'数据二',
              routeName:'extract-one'
            }
          ]
        },
        {
          name:'数据三',
          routeName:'data-model',
          child:[
            {
              name:'数据三',
              routeName:'model-one'
            }
          ]
        },
        {
          name:'数据四',
          routeName:'data-property',
          child:[
            {
              name:'数据四',
              routeName:'property-one'
            }
          ]
        }
      ]
    }
  },
  props:['routeName'],
  mounted(){
    this.pathName = this.routeName
  },
  methods:{
    handleChangeData(routeName){
      this.$router.push(routeName)
    }
  }
}
</script>
<style lang="scss" scoped>
  .nav{
    flex:20%;
    min-width:150px;
    height:calc(100vh - 30px);
    background:#304156;
  }
</style>
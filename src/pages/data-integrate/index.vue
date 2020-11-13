<template>
  <div class="data-integrate">
    <div class="nav">
      <sideBar :routeName="$route.name"></sideBar>
    </div>
    <div class="container">
      <router-view></router-view>
    </div>
  </div>
</template>
<script>
import sideBar from '../../components/sideBar'
export default {
  data(){
    return {

    }
  },
  components:{
    sideBar
  },
  mounted(){
    
  },
  methods:{
    handleChange(){
      this.$router.push('/data-one')
    },
    handleData(){
      this.$router.push('/data-two')
    }
  }
}
</script>
<style lang="scss" scoped>
  .data-integrate{
    display:flex;
    .nav{
      flex:20%;
      min-width:150px;
      height:calc(100vh - 30px);
      background:#304156;
    }
    .container{
      margin-left:20px;
      flex:80%;
      display:flex;
      align-items: center;
      justify-content: center;
    }
  }
</style>
<style lang="scss">
  .el-collapse-item__header{
    background:rgb(48, 65, 86);
    color:#fff;
    border-bottom:none;
    padding-left:10px;
  }
  .el-collapse-item__wrap{
    background: #1f2d3d!important;
  }
  .el-collapse-item__content{
    padding:15px;
    color:#fff;
  }
</style>
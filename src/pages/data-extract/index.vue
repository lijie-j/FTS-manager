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
  methods:{
    handleChange(){
      this.$router.push('/extract-one')
    },
    handleData(){
      this.$router.push('/extract-two')
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
      height:calc(100vh - 40px);
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
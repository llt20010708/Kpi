<template>
  <div id="loginWrapper">
    <div id="loginConnect">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>注册界面</span>
          <el-button style="float: right; padding: 3px 0" type="text">忘记密码</el-button>
        </div>
        <div id="loginContentBody">
            <el-input id="newusername" v-model="newuser.newusername" clearable></el-input>
            <el-input id="newpassword" v-model="user.newpassword" show-password clearable></el-input>
        </div>
        <div id="loginSubmit">
            <el-button id="systemSubmit"  @click="loginsystem">注册</el-button>
           
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
import Axios from 'axios'
export default {
  name:'register',
    data(){
        return{
            newuser:{
                newusernmae:"",
                newpassword:""
            }
        }
    },

method:{
  loginSystem(){
    Axios.get('http://localhost:3000/register'),{
      
    }.then(function(response){
      alert(response.data)
    })
  }
  }
}
</script>

<style>
    #loginWrapper{
        /* background-color: thistle; */
        height: 100%;
    }
    #loginConnect{
        width: 400px;
        margin: 0 auto;
        padding-top: 100px;
    }
    #systemSubmit{
        display: block;
        margin: 0 auto;
        background-color: #0a9588;
        color: white;
        border-color: #0a9588;
    }
    #password{
      margin-top: 5px;
      margin-bottom: 8px;
    }

</style>
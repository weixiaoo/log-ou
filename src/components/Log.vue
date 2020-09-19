<template>
    <div id="log-main">
      <form action="" @submit="checkForm" class="log-form">
        <p>
          <label for="name">名字</label>
          <input type="text" id="name" name="name" v-model="name">
        </p>
        <p>
          <label for="passwd">密码</label>
          <input type="password" id="passwd" name="passwd" v-model="passwd">
        </p>
        <p>
          <input type="submit" value="提交">
        </p>  
        <p v-if="errors.length">
          <b>请输入名字和密码</b>
          <ul>
            <li v-for="error in errors" :key="error.index">{{error}}</li>
          </ul>
        </p>
      </form>
    </div>
</template>

<script>
export default {
  name: 'Log',
  data() {
    return {
      name:null,
      passwd:null,
      errors:[]
    }
  },
  methods: {
    checkForm:function(e) {
      if(this.name && this.passwd) {
        return true
      }

      this.errors = []
      if(!this.name) {
        this.errors.push('名字')
      }
      if(!this.passwd) {
        this.errors.push('密码')
      }

      e.preventDefault();
    }
  }

} 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
 #log-main {  
   position: absolute;
   top: 50%;
   left: 50%;
   margin:200px 0 0 -300px;
 }
 .log-form {  
   height: 400px;
   width: 600px;
   border: 1px solid #eee;
   font-size: 25px;
   text-align: center;
   overflow: hidden;
   background-color: #eee;
   box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
 }
 .log-form p {
   margin-top: 45px;
 }
 input {
   border: 1px solid red;
 }
</style>
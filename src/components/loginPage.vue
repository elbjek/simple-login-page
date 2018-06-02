<template>
  <div class="hello">

    <form action="" id="form" @submit.prevent="validation">

     <label for="">
        <input type="text" v-model="email" placeholder="Username/Email">
        <a href="#" @click="showPass()"> <img src="../assets/checkmark.png" alt=""></a>
        
     </label>
      <p>{{emailError}}</p>
     <label for=""> 
        <input :type="passtype" v-model="password" placeholder="Password"> 

        <a href="#" @click="showPass()"> <img src="../assets/eye-open.png" alt=""></a>
     </label>
    <p>{{passError}} </p>

  <button type="submit">Login</button>
    </form>

  </div>
</template>

<script>
export default {
  name: 'loginPage',
  data(){

    return{
      show:false,
      passtype:"password",
      password:"",
      email:"",
      emailError:"",
      passError:""
    }
  },
  methods:{
    showPass(){
      if(this.passtype=="password"){
        this.passtype = "text"
      } else{
        this.passtype="password"
      }
    },
    regEx(){
      var regularExpresion = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
       return regularExpresion.test(this.email);   
    },
    validation(){
   
      // console.log("im here",this.password, this.email);
      if(!this.regEx(this.email) ){
      this.emailError = "E-mail doesn't exist."
      } else if(this.email == ""){
      this.emailError = "E-mail is required."
      }
       if(this.password == ""){
        this.passError = "Password is required."
        // console.log(this.password)
      } else if (this.password.length < 3){
        this.passError = "Password needs to be at least 3 characters long."
        console.log(this.password)
        
      }

    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang='scss'>

  #form{
  display:flex;
  margin: 0 auto;
  width:50%;
  // justify-content: flex-start;
  flex-direction: column;

  label{

    display: flex;
    justify-content: center;
    align-items: center
  }
  input{
    background-color: rgba($color: #ffffff, $alpha: 0.1);
    padding:10px;
    width:35%;
    margin:5px;
    border:3px solid   rgba($color: #ffffff, $alpha: 0.8);
    border-radius: 50px;
    cursor: pointer; 
    position: relative;
    &:hover{
      border:3px solid   rgba($color: #ffffff, $alpha: 1);
    }

  }
img{
  height:20px;
  //  position: absolute;
  // right: 0;
}


  ::placeholder{
    color:#222222;
    font-weight: bolder;
      }
    
  
  button{
    // width:100px;
    margin:0 auto;
    background-color: rgba(51,78,145,1);
    border:1px solid white;
    padding:15px 50px;

}

}
</style>

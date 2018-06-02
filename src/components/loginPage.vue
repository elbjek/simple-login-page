<template>
  <div  >
    <h1>{{welcomeMsg}}</h1>
    <form action=""  @submit.prevent="validation">
        <div >
          <label for="email">
          <input type="text"  name="email" v-model="email" placeholder="Username/Email">
          </label>
          <p>{{emailError}}</p>
        </div>
        <div >
          <label for="password"> 
          <input :type="passtype" name="password" @click="showIcon()" v-model="password" placeholder="Password"> 
          <a href="#" v-if="show" @click="togglePassword()"> <img src="../assets/eye-open.png" alt=""></a>
          </label>
          <p>{{passError}} </p>
          <button  type="submit">Login</button>
        </div>
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
         passError:"",

       }
     },
     methods:{
       showIcon(){
         this.show = true;
       },
       togglePassword(){
         this.show=true;
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
         if(this.email == ""){
         this.emailError = "E-mail is required."
         }
         else if(!this.regEx(this.email) ){
         this.emailError = "Please enter a valid e-mail."
         }
          
          if(this.password == ""){
           this.passError = "Password is required."

         } else if (this.password.length < 3){
           this.passError = "Password needs to be at least 3 characters long."
         }
         else{
           this.password=""
           this.email=""
         }
   
       }
     }
   
   }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang='scss'>

     form{
        display:flex;
        flex-direction: column;
        justify-content: space-between;
       align-items: center;
       width:30%;
       margin:0 auto;

     label{
        display: flex;
        align-items: center;  
        position: relative;

       input{
         background-color: rgba(#ffffff, 0.2);
         border:3px solid rgba(#ffffff, 0.8);
         border-radius: 10px;
        padding:10px 100px 10px 5px;
        font-weight: bold;
      &:hover{
            background-color: rgba(#ffffff, 0.4);
            border:3px solid rgba(#ffffff, 1);
        
         }
       }
      ::placeholder{
        color:white;
        // font-weight: ;
      }
      img{
        height:15px !important;
        opacity: 1 !important; 
        position:absolute;
        left:150px;
        top:5px;
        transform: translate(-200,0)
      }
     }
      button{
           background-color:  rgba(#ffffff,1);
           border:none;
           padding:10px 23px;
           border-radius: 10px;
           color:rgba(51,78,145,1) ;
           margin-top: 10px;
         }
         p{
           font-size: 15px;
         }
  }
         

   
</style>
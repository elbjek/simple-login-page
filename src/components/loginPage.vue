<template>
  <div class="hello">

    <form action="" id="form">

     <label for="">
        <input type="text" placeholder="Username">
     </label>

     <label for="">
        <input type="text" placeholder="Password">
     </label>


  <button>Login</button>
    </form>

  </div>
</template>

<script>
export default {
  name: 'loginPage',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang='scss'>
#form{
  display:flex;
  margin: 0 auto;
  width:50%;
  justify-content: center;
  flex-direction: column;
  input{
    background-color: rgba($color: #ffffff, $alpha: 0.1);
    padding:10px;
    width:30%;
    margin:5px;
    border:3px solid   rgba($color: #ffffff, $alpha: 0.8);
    border-radius: 10px;
    cursor: pointer;
  }
  ::placeholder{
    color:#222222;
    font-weight: bolder;
  }
  button{
    width:100px;
    margin:0 auto;
  }
}
</style>

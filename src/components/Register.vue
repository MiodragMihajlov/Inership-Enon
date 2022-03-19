<template>

<h2>Welcome</h2>
  <div class="login">
    <div class="form">
      
        <input type="text" placeholder="Username"  v-model.trim="form.name" />
        <input type="text" placeholder="Email" v-model.trim="form.email" />
        <input type="password" placeholder="Password" v-model.trim="form.password" />
         <input type="password" placeholder="Confirm password" v-model.trim="form.confPassword" />
        <button @click="userRegister">Register</button>


  </div>
  </div>

  <p>{{info}}</p>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      info: "",
      form: {
        name: "",
        password: "",
        email: "",
        confPassword: "",
      },
    };
  },

  methods: {
    async userRegister() {
      if (
        this.form.name == "" ||
        this.form.password == "" ||
        this.form.email == ""
      ) {
        this.info = "Unesite sve podatke!";
        return;
      }
       if (
        this.form.password != this.form.confPassword
      ) {
        this.info = "Invalid password!";
        return;
      }
      try {
        const res = await axios.post(
          "http://576e122.e2.mars-hosting.com/api/plan-vezbanja/workout-register",
          this.form
        );
        
        console.log(res);
        alert(res.data.message);
        this.info = res.data.message;

        if(res.data.message == "Successfully registered!"){
            this.$router.replace({name:"login"});
        }
      
      }catch (error) {
        console.warn(error);
      }
    },
  },
};
</script>

<style scoped>
.login {
  width: 30%;
  height: 100%;
  border: 1px solid #CCC;
  /* background: url(https://media0.giphy.com/media/XRkoMgzO6NVfy/giphy.gif) center center no-repeat; */
  /* background: url(../images/workout-wallpaper-fitness-wallpaper.jpg) center center no-repeat; */
  background-color: #C8D0A9;
  background-size: cover;
  margin: 2% auto;
  border-radius: 20px;
}
.login .form {
  height: 100%;
  padding: 15px 25px;
}
 h2 {
  color: black;
  font-weight: bolder;
  text-align: center;
  font-weight: bold;
  font-size: 22px;
  margin-top: 1px;
  margin-bottom: 30px;
  text-shadow: 1px 1px 3px white;
}
.login .form input,button{
  width: 100%;
  height: 40px;
  margin-top: 2%;
  /* background: rgba(255,255,255,.5); */
  /* border: 1px solid rgba(255,255,255,.1); */
  padding: 0 5% 0 5% !important;
  /* color: #FFF; */
  border-radius: 5px;
  font-size: 14px;
   z-index: 1;
}
.login .form input:focus {
  /* border: 1px solid rgba(255,255,255,.8); */
  outline: none;
  /* color: black; */
}
.login .form input{
  width: 90%;
  /* background: rgba(255,255,255,.5);
  border: 1px solid rgba(255,255,255);
  color: black; */
  margin: 1% 5% 2% 5% !important;
  z-index: 1;
}
/* ::-webkit-input-placeholder {
    color: white;
} */
.login .form button {
  /* background: rgba(255,255,255,.9);
  color: #444; */
  font-size: 15px;
  margin-top: 20%;
  font-weight: bold;
  z-index: 1;
}
/* .login button:hover{
  background-color: rgba(255,255,255,.8);
} */
@media screen and (max-width: 740px) {
.login{
    width: 40%;
  }
  #menu{
    height: 5%;
  }
}
@media screen and (max-width: 640px) {
.login{
    width: 50%;
  }
}
@media screen and (max-width: 420px) {
  .login{
    width: 60%;
  }
}
</style>
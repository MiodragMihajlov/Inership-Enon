<template>
    <div class="wrapper">


              <div class="info">

                 <h1>HI {{this.user.usr_name}} </h1>   
                <h2>You selected {{usrWop}} exercises </h2>
                 <h2>And your current workout level is {{usrLvl}} </h2>
                 <h2> {{message}}</h2>

</div>

    </div>
</template>

<script>
import axios from 'axios'
import { mapState } from "vuex";

    export default {

       data(){

            return{     

                    usrLvl:"",
                    usrWop:"",
                    message:""
                   


                  
            }

       },
       mounted(){

            this.getUserData();

       },


        computed: {
    ...mapState(["isLoggedIn", "user", "sid","isAdmin"])}
    ,


    methods:{

                async getUserData() {
      
      const params = {
        usrId: this.user.usr_id
       
      };
      try {
        const res = await axios.post(
          "http://576e122.e2.mars-hosting.com/api/plan-vezbanja/usr-workout-info",
          params
        );
        console.log(res)
        this.usrLvl=res.data.wkData.lvl_name;
        this.usrWop=res.data.wkData.wop_name;
        this.message=res.data.message;
      } catch (eror) {
        console.log(eror);
      }
    },

    }



    



    
        
    }
</script>

<style scoped>


  .wrapper{

display:flex;
justify-content: center;
align-items: center;

  }

  .info{

    display:flex;
    flex-direction: column;
    margin-bottom :40px;
  }


</style>
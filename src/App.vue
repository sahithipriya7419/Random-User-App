<template>
  <main>
    <div class="app p-4 container fluid">
      <div class="row">
        <div class="col col-md-4 mt-4 offset-md-4">
           <div class="text-center">
              <div v-if="user">
                 <userCard :user="user"></userCard>
                 <button
                 type="button"
                 @click="fetchUser"
                  class="btn btn-primary btn-large mt-3">
                  Fetch new user
                 </button>

              </div>
              <div v-else class="text-center">
                <div class="spinner-border spinner-grow" role="status">
                </div>
                <div class="text-white">Loading...</div>
              </div>
           </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios"
import userCard from "./components/userCard.vue"

export default {
  name:"App",
  components:{userCard},
  data()
  {
    return{
      user: null,
    }
  },
  mounted()
  {
    this.fetchUser();
  },
  methods:{
    fetchUser(){
       axios.get("https://randomuser.me/api/")
       .then((res)=>{console.log(res);
        this.user = res.data.results[0]
      })
    }
  }
}
</script>

<style>
  main{
    height:100vh;
    background-image: url('./assets/bg.jpg');
    background-position: center;
    background-size: cover;
  }
  .card{
    margin-top: 120px;
  }
  .img{
    margin-top: -80px;

  }
</style>
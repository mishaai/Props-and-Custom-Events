<template>
  <section>
    <ActiveUser :db="userdata"></ActiveUser>
    <UserData @out="changedata"></UserData>
  </section>
</template>

<script>

import ActiveUser from './components/ActiveUser.vue'
import UserData from './components/UserData.vue'

export default {
    
    data(){
        return{
            userdata:[{
                name:'Mikheil Nadiradze',
                age:37
            }],

        }
    },
    components:{
        ActiveUser,
        UserData,
    },
    methods:{
        changedata(event){
            this.userdata = event           
        }
    }
}
</script>

<style>

</style>
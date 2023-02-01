<template >
    
    
    <div class="row flex-nowrap body">
         <SideBar/>
         <div class="col m-0 p-0">
            <Header/>
            <div class="row m-4">
              <IdeationCard/>
              <div class="col-4" >
                 <Collaborate/>
                 <InteractionCard/>
              </div>
           </div>
         </div>
     </div>

</template>

<style>
.body{
margin: 0;
padding: 0;
background-color: #F0F2FA;
}
</style>

<script setup>
import Collaborate from '../Collaborate.vue';
import IdeationCard from './IdeationCard.vue';

</script>
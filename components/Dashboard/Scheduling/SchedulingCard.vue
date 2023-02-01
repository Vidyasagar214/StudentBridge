<template >

    <div class="col-12" >
      <div class="card bg-white scheduling-card">
          <div class="title">
              <h5 class="m-0 p-0">Holiday Videos</h5>
              <font-awesome-icon :icon="['fas', 'chevron-right']" class="mx-3"/>
              <h5 class="m-0 p-0">Thanksgiving</h5>
          </div>
          <Stepper class="p-3"/>
           <Calender/>
       </div>
       </div>


</template>

<style>
.scheduling-card{
    height: 100%;
}
.title{
    height:50px;
    display: flex;
    align-items: center;
    padding: 15px;
    border-bottom: 2px solid #EDEFF2;
}

</style>

<script setup>
 import Stepper from './Stepper.vue';
 import Calender from './Calender.vue';
</script>
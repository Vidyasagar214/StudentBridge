<template >

       <div class="card bg-white create-video">
        <div class="card-body">
         <div>
              <p class="card-text text-start fw-bold mb-4">Let's create some new videos...</p>
              <div class="text-center m-auto ">
              <NuxtLink to="/dashboard/ideation"><button class="btn px-5 create-video-btn fw-bold m-auto" type="button"><font-awesome-icon :icon="['fas', 'video']" class="me-3"/>Create video</button></NuxtLink>
            </div>
         </div>
       </div>
       </div>
   
</template>

<style>
.create-video{
    height: 150px;
}
.create-video-btn{
    background-color: #a3db00;
}
</style>

<script setup>
 
</script>
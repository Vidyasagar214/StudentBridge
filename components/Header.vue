<template >
   <nav class="navbar sticky-top bg-white border border-bottom">
    <div class="container-fluid ">
        <div class="d-flex align-items-center">
            <img src="../assets/carthage college...png" width="180px" height="50px" class="border " alt="">
         </div>

         <div class="d-flex justify-content-between align-items-center">
           <div class="rounded-pill bg-secondary px-3 py-1 text-white fw-semibold me-2"><font-awesome-icon :icon="['fas', 'circle-dollar-to-slot']" class="me-2"/>06 Credits</div>
           <span class="mx-3 bg-secondary py-1 px-2 rounded-circle text-white"><font-awesome-icon :icon="['fas', 'bell']" /></span>
           <span class="vr text-muted">|</span>
           <div class="mx-2">
               <img  src="../assets/katie1.jpg" height="40" width="40" class="border rounded-circle mx-1" alt="">
               <span class="profile">Katy Ball</span>
           </div>
         </div>
    </div>
   </nav>
</template>

<style>
.profile{
  font-weight: 500;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 14px;
}
</style>
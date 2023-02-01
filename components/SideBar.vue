<template>
 
      <div class="col-2  sidebar-container p-0">
            <div class="d-flex flex-column align-items-start pt-2 text-white min-vh-100">
               
                <div class="d-flex align-items-center mb-md-0 me-md-auto mx-auto text-white text-decoration-none">
                  <NuxtLink to="/">
                  <img src="../assets/SB_Logo.jpg" alt="" width="160" height="40"></NuxtLink>  
                    <font-awesome-icon :icon="['fas', 'bars']" class="mx-3"/>
                  </div>

                <hr class="bg-white  mx-3" style="width:80%"> 

                <ul class="nav flex-column p-0 m-0">
                  <li class="nav-item bg-secondary  border-start border-3 border-white active-nav py-1">
                     <NuxtLink to="/" class="nav-link active text-white"><font-awesome-icon :icon="['fas', 'lightbulb']" class="mx-3"/>Dashboard</NuxtLink>
                  </li>

                  <li class="nav-item py-1">
                     <NuxtLink to="/" class="nav-link text-secondary" ><font-awesome-icon :icon="['fas', 'circle-play']" class="mx-3"/>My videos</NuxtLink>
                   </li>

                   <li class="nav-item py-1">
                      <NuxtLink to="/" class="nav-link text-secondary" ><font-awesome-icon :icon="['fas', 'chart-simple']" class="mx-3"/>My activities</NuxtLink>
                   </li>
                  
                </ul>
            </div>
        </div>
 
</template>

<style>
.sidebar-container{
  background-color: #323e48;
}
.active-nav{
    width:136%
}
</style>
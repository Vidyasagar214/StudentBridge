<template >

    <div class="card bg-white missioncontrol-card mb-4">
     <div class="card-body  ">
      <div>
       <p class="card-title text-start fw-bold">Mission control</p>
       <!-- <b-list-group>
         <b-list-group-item href="#" variant="secondary" class="mb-1">
            <b-image></b-image>
         </b-list-group-item>
         <b-list-group-item href="#" variant="secondary" class="mb-1">Warning list group item</b-list-group-item>
         <b-list-group-item href="#" variant="secondary" class="mb-1">Info list group item</b-list-group-item>
         <b-list-group-item href="#" variant="secondary" class="mb-1">Light list group item</b-list-group-item>
         <b-list-group-item href="#" variant="secondary" class="mb-1">Light list group item</b-list-group-item>
         <b-list-group-item href="#" variant="secondary" class="mb-1">Light list group item</b-list-group-item>
       
       </b-list-group> -->
       
      <b-list-group >
      <b-list-group-item class="d-flex align-items-center p-1 border-0 bg-light mb-1">
        <b-avatar class="mr-2" rounded> <font-awesome-icon :icon="['fas', 'pen']" size="lg"/></b-avatar>
        <span class="mr-auto">Created<br><span class="text-primary ">Nov 12, 2022</span></span>
      </b-list-group-item>
      <b-list-group-item class="d-flex align-items-center p-1 border-0 bg-light mb-1">
        <b-avatar rounded class="mr-2"><font-awesome-icon :icon="['fas', 'calendar']" size="lg"/></b-avatar>
        <span class="mr-auto">Deadline<br><span class="text-primary ">Nov 20, 2022</span></span>
      </b-list-group-item>
      <b-list-group-item class="d-flex align-items-center  p-1 border-0 bg-light mb-1">
        <b-avatar variant="info" rounded src="../../assets/Brent Mitchell.jpg" class="mr-2"></b-avatar>
        <span class="mr-auto p-0">Creative director<br><span class="text-primary">Brent Mitchell</span></span>
        <font-awesome-icon :icon="['fas', 'pencil']" class="text-secondary" role="button"/>
      </b-list-group-item>
      <b-list-group-item class="d-flex align-items-center  p-1 border-0 bg-light mb-1">
        <b-avatar variant="info" rounded src="../../assets/Jane.jpg" class="mr-2"></b-avatar>
        <span class="mr-auto">Producer<br><span class="text-primary ">Jane</span></span>
        <font-awesome-icon :icon="['fas', 'pencil']" class="text-secondary" role="button"/>
      </b-list-group-item>
      <b-list-group-item class="d-flex align-items-center p-1 border-0 bg-light mb-1">
        <b-avatar variant="info" rounded src="../../assets/Bryan.jpg" class="mr-2"></b-avatar>
        <span class="mr-auto">Approver<br><span class="text-primary ">Bryan Feraric</span></span>
        <font-awesome-icon :icon="['fas', 'pencil']" class="text-secondary" role="button"/>
      </b-list-group-item>
      <b-list-group-item class="d-flex align-items-center p-1 border-0 bg-light">
        <b-avatar rounded class="mr-2"><font-awesome-icon :icon="['fas', 'calendar']" size="lg"/></b-avatar>
        <span class="mr-auto">Filming date range<br><span class="text-primary ">Nov 15,2022-Nov 20,2022</span></span>
        <font-awesome-icon :icon="['fas', 'pencil']" class="text-secondary" role="button"/>
      </b-list-group-item>
      
    </b-list-group>
      
     </div>
    </div>
    </div>

</template>

<style>
.missioncontrol-card{
  max-height:100%
}
</style>
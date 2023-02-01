<template >

    <div class="col-8" >
      <div class="card bg-white bigcard">
       <div class="card-body d-flex text-center justify-content-center align-items-center ">
        <div>
            <h2 class="card-title text-center">No Videos</h2>
            <p class="p-0 m-0 text-center fw-semibold">Let's get started with managing all your content.</p>
            <p class="card-text text-center fw-semibold">Right now....</p>
            <button class="btn create-video-btn px-5 fw-bold" type="button"><font-awesome-icon :icon="['fas', 'video']" class="me-3"/>Create video</button>
        </div>
       </div>
       </div>
   </div>

</template>

<style>
.bigcard{
    height: 500px;
}
.create-video-btn{
    background-color: #a3db00;
    color:#323e48 ;
}
.create-video-btn:hover{
    background-color: #323e48;
    color:white;
}


</style>
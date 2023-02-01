<template >
  <div class="card bg-white collaborate-card">
        <div class="card-body d-flex justify-content-between align-items-top ">
         <div>
          <p class="card-title text-start fw-bold">Collaborate</p>

          <div class="comments">
          <div class="mt-2 p-1">
                <div class="d-flex justify-content-between align-items-end">
                    <div class="d-flex align-items-end">
                      <img src="../../assets/Bryan.jpg" width="40" height="40" class="rounded me-2">
                      <div class="text-primary">John Krik</div>
                    </div>
                    <div class="text-secondary text-end ps-5"><small> 12:45 PM</small></div>
                </div>  
                <div class="shadow-sm border border-light bg-light rounded mt-1 p-1">
                   <p class="fs-6 text-muted mb-0 p-0 m-0 lh-1">We would need to consider few clips covering dance performances we had last year. </p>
             </div>
         </div> 
         <div class="mt-3 p-1 ">
                <div class="d-flex justify-content-between align-items-end">
                    <div class="d-flex align-items-end">
                      <img src="../../assets/Bryan.jpg" width="40" height="40" class="rounded me-2">
                      <div class="text-primary">John Krik</div>
                    </div>
                    <div class="text-secondary text-end ps-5"><small> 12:45 PM</small></div>
                </div>  
                <div class="shadow-sm border border-light bg-light rounded mt-1 p-1">
                   <p class="fs-6 text-muted mb-0 p-0 m-0 lh-1">I dont have any idea where the clips are saved. @Adrianna  would you have some idea?</p>
             </div>
         </div> 
         <div class="mt-3 p-1 ">
                <div class="d-flex justify-content-between align-items-end">
                    <div class="d-flex align-items-end">
                      <img src="https://i.imgur.com/zQZSWrt.jpg" width="40" height="40" class="rounded me-2">
                      <div class="text-primary">Adrianna Jones</div>
                    </div>
                    <div class="text-secondary text-end ps-5"><small> Just now</small></div>
                </div>  
                <div class="shadow-sm border border-light bg-light rounded mt-1 p-1">
                   <p class="fs-6 text-muted mb-0 p-0 m-0 lh-1">I have uploaded the video, @John  let me know if you need anything else. Cheers !!</p>
             </div>
         </div> 
        </div>
         <div class="mt-4 d-flex flex-row justify-content-evenly align-items-center  form-color">
            <font-awesome-icon :icon="['fas', 'paperclip']" class="me-3 text-secondary"/>
            <font-awesome-icon :icon="['fas', 'image']" class="me-3  text-secondary"/>
           <div >
              <input class="form-control comment-box me-2" type="text" placeholder="Type Comment">
           </div>
           <font-awesome-icon :icon="['fas', 'paper-plane']" class=" text-success"/>
       </div>
         
     </div>  

        </div>
       </div>
      

</template>

<style>

.collaborate-card{
 max-height:100%
}
.comments{
  max-height:250px;
 overflow-y: scroll;
}
/* width */
.comments::-webkit-scrollbar {
  width: 5px;
}
/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1; 
  border-radius: 10px;
} 
/* Handle */
::-webkit-scrollbar-thumb {
  background:lightgray;
  border-radius: 10px; 
  
}
/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: rgb(110, 110, 110); 
 
}
.comment-box{
    border-left: none;
    border-right: none;
    border-top: none;
    border-radius: 0px;
}
.comment-box:focus {
    color: #464b50;
    background-color: #fff;
    border-color: #35b69f;
    outline: 0;
    box-shadow: none;
}


</style>
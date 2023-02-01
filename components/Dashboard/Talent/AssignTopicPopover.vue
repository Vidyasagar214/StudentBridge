<template>
    <div>
        <b-sidebar id="sidebar-right" backdrop right shadow class="overflow-auto">
      <div class="px-2 pb-5  assigntopic ">
        <p class="text-center p-0 fw-bold">Assign topic</p>
        <b-card class="mb-3 ">
        <b-form-group label="Talent" label-for="talent"  required>
          <b-input placeholder="Talent" type="text" value="Alexis" disabled></b-input>
        </b-form-group>
        <div class="mb-2">Key messages</div>
        <div class="accordion" role="tablist">
       <b-card no-body class="mb-2">
        <b-card-header header-tag="header" class="p-1" role="tab">
          <b-button block v-b-toggle.accordion-1 variant="light" class="text-left">Lorem ipsum dolor sit amet consectetur adipisicing elit.</b-button>
        </b-card-header>
        <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel" class="px-1 m-0">
        <b-card-body class="p-0 m-0">
          <b-form-checkbox id="checkbox-1" name="checkbox-1" class="mb-2 py-2 border-bottom">
             Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
          <b-form-checkbox id="checkbox-2"  name="checkbox-2" class="mb-2 py-2 border-bottom" >
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
          <b-form-checkbox id="checkbox-3"  name="checkbox-3" class="mb-2 py-2 ">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
        </b-card-body>
      </b-collapse>
    </b-card>

    <b-card no-body class="mb-1">
        <b-card-header header-tag="header" class="p-1" role="tab">
          <b-button block v-b-toggle.accordion-1 variant="light" class="text-left">Lorem ipsum dolor sit amet consectetur adipisicing elit.</b-button>
        </b-card-header>
        <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel" class="px-1 m-0">
        <b-card-body class="p-0 m-0">
          <b-form-checkbox id="checkbox-1" name="checkbox-1" class="mb-2 py-2 border-bottom">
             Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
          <b-form-checkbox id="checkbox-2"  name="checkbox-2" class="mb-2 py-2 border-bottom" >
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
          <b-form-checkbox id="checkbox-3"  name="checkbox-3" class="mb-2 py-2 ">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque, iusto.
          </b-form-checkbox>
        </b-card-body>
      </b-collapse>
    </b-card>
    </div>
      </b-card>
      <b-button variant="success" class="float-right"><font-awesome-icon :icon="['fas', 'clipboard-check']" class="mr-2 "/>Assign</b-button>
      </div>
    </b-sidebar>
    </div>
</template>

<script >
 export default {
    props: ['id'],
  };
</script>

<style >

.b-sidebar > .b-sidebar-body{
  overflow: hidden;
}
.assigntopic{
  max-height:600px;
  overflow-y: scroll;
}
/* width */
.assigntopic::-webkit-scrollbar {
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


</style>
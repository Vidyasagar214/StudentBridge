<template>
  <div>
      <b-sidebar id="sidebar-right" backdrop right shadow class="overflow-auto">
    <div class=" pb-5 ">
      <p class="text-center pb-2 fw-bold border-bottom">Create Project</p>
      <div class="mb-3 px-3">
      <b-form-group label="Project name"   required>
        <b-input placeholder="Text" type="text"  ></b-input>
      </b-form-group>
      <b-form-group label="Project deadline"   required>
        <b-datepicker placeholder="day,month date,year"  ></b-datepicker>
      </b-form-group>
      <b-form-group label="Number of videos"  required>
        <b-input placeholder="0 Videos" type="text" ></b-input>
      </b-form-group>
      <b-form-group label="Talent" label-for="talent"  required>
        <b-textarea placeholder="Text" type="text"  ></b-textarea>
      </b-form-group>
      <b-button variant="success" class="float-right"   @click="hide">
        <font-awesome-icon :icon="['fas', 'file']" class="mr-2 "/>Create Project
      </b-button>
    </div>
   
    </div>
  </b-sidebar>
  </div>
</template>

<script >
export default {
  props: ['id'],
};
</script>

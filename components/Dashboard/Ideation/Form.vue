<template>
  <div class="m-4">
    <b-form  ref="ideation"  @submit.prevent="submitForm" novalidate >

      <b-row>
        
        <b-col lg="9">
          <b-form-group label="Project name" label-for="project"  required>
            <template slot="label">
                Project name<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-select
              id="projectname"
              v-model="projectname"
            >
              <b-select-option  >Select Project</b-select-option>
              <b-select-option value="Holiday Video">Holiday Videos</b-select-option>
              <b-select-option value="Placements 2022">Placements 2022</b-select-option>
              <b-select-option value="Admissions 2023">Admissions 2023</b-select-option>
          </b-form-select>
          </b-form-group>
        </b-col>

          <b-col lg="3" class="mt-4">
    <b-button variant="outline-secondary" class="mt-2 px-2" v-b-toggle.sidebar-right>
       <font-awesome-icon :icon="['fas', 'plus']" class="me-1 text-secondary" />Create Project
    </b-button>
  </b-col>

        <b-col lg="12">
          <b-form-group label="Video title" >
            <template slot="label">
                Video title<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-input
            id="videotitle"
              v-model="videotitle"
              placeholder="Text"
            ></b-form-input>
          </b-form-group>
        </b-col>

        <b-col lg="6">
          <b-form-group label="" >
            <template slot="label">
                Video length<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-input
               type="time"
               id="videolength"
              v-model="videolength"
              placeholder="MM:SS"
            ></b-form-input>
          </b-form-group>
        </b-col>

        <!-- <b-col lg="6" md="6" sm="6">
            <label >Video length<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/></label>
       <b-input-group class="mb-3">
      <b-form-input
        v-model="videolength"
        type="time"
        placeholder="HH:mm:ss"
      ></b-form-input>
      <b-input-group-append>
        <b-form-timepicker
          v-model="videolength"
          button-only
          right
          show-seconds
          locale="en"
        ></b-form-timepicker>
      </b-input-group-append>
    </b-input-group>
        </b-col> -->
     
        <b-col lg="6" md="6" sm="6">
          <b-form-group >
          <template slot="label">
             Video deadline<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-datepicker
              id="deadline"
              v-model="deadline"
              placeholder="Choose the end date"
            ></b-form-datepicker>
          </b-form-group>
        </b-col>

        <b-col lg="12" md="12" sm="12">
          <b-form-group >
            <template slot="label">
                Video description<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-textarea
              id="description"
              v-model="description"
              placeholder="Text"
            ></b-form-textarea>
          </b-form-group>
        </b-col>
    
        <b-col lg="4" md="4" sm="4">
          <b-form-group  >
            <template slot="label">
                Producer<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-select
            id="producer"
              v-model="producer"
            >
              <b-select-option  >Select </b-select-option>
              <b-select-option value="StudentBridge">StudentBridge</b-select-option>
              <b-select-option value="Internal">Internal</b-select-option>
              <b-select-option value="UGC">User generated content</b-select-option>
              <b-select-option value="CVN">Certfied vendor network</b-select-option>
          </b-form-select>
          </b-form-group>
        </b-col>

        <b-col lg="4" md="4" sm="4">
          <b-form-group >
            <template slot="label">
                Creative director<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-select
              v-model="creativedirector"
              id="creativedirector"
            >
              <b-select-option  >Select </b-select-option>
              <b-select-option value="Brent">Brent Mitchell</b-select-option>
              <b-select-option value="Foster">Rick Foster</b-select-option>
              <b-select-option value="Karen">Karen Doe</b-select-option>
          </b-form-select>
          </b-form-group>
        </b-col>

        <b-col lg="4" md="4" sm="4">
          <b-form-group >
            <template slot="label">
                Approver<span class="required">*</span>
                  <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
                </template>
            <b-form-select
              v-model="approver"
              id="approver"
            >
              <b-select-option   >Select</b-select-option>
              <b-select-option value="Elizabeth">Elizabeth Young</b-select-option>
              <b-select-option value="Bryan">Bryan</b-select-option>
              <b-select-option value="Henry">Henry Nichol</b-select-option>
          </b-form-select>
          </b-form-group>
        </b-col>
      </b-row>
  
      
      <div class="mt-3 d-flex justify-content-between">
        <b-button type="reset" variant="secondary" class="mr-3">Cancel</b-button>
        <b-button type="submit" variant="success">Create video</b-button>
      </div>
    </b-form>
    <CreateProjectOverlay/>
    <p v-if="success"> {{ success }}</p>
    <pre>{{ response }}</pre>
  </div>
</template>

<script >
import axios from "axios";
import CreateProjectOverlay from './CreateProjectOverlay.vue';

export default {
  components: { CreateProjectOverlay },
  data() {
    return {
      form: {
      loading: true,
      userID: 1,
      projectname: "",
      videotitle: "",
      videolength: "",
      deadline: "",
      description: "",
      producer: "",
      creativedirector: "",
      approver: "",
      response: '',
      success: '',    
   } }},
 
  methods: {
    submitForm(event) {
      axios.post('https://625fecb853a42eaa07fd7020.mockapi.io/users', {
        userID: this.userID,
        projectname: this.projectname,
        videotitle: this.videotitle,
        videolength: this.videolength,
        deadline: this.deadline,
        description: this.description,
        producer: this.producer,
        creativedirector: this.creativedirector,
        approver: this.approver,
      }).then(response => {
        // console.log(response);
        this.success = 'Data saved successfully';
        this.response = JSON.stringify(response, null, 2)
        alert("Form Submitted Successfully")
      }).catch(error => {
        this.response = 'Error: ' + error.response.status
      })
      // this.$refs.ideation.reset()
      event.target.reset()
    }
  }
};
</script>

<style >
.required {
  color: red;
}
</style>




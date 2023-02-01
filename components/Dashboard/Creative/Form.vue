<template>
    <div class="m-4">
 
      <b-form @submit="onSubmit" @reset="onReset" v-if="show" novalidate >

<b-row>
  
  <b-col lg="12">
    <b-form-group label="Video title" label-for="video">
      <template slot="label">
          Video purpose<span class="required">*</span>
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
      <b-form-input
        id="video"
        v-model="form.video"
        placeholder="Text"
      ></b-form-input>
    </b-form-group>
  </b-col>

  <b-col lg="12" md="12" sm="12">
    <b-form-group label="Project name" label-for="project"  required>
      <template slot="label">
         Video style<span class="required">*</span>
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
      <b-form-select
        id="project"
        v-model="form.project"
        :options="videostyle"
      ></b-form-select>
    </b-form-group>
  </b-col>
  
  <b-col lg="12" md="12" sm="12" class="mt-3 mb-4">
  <b-card no-body>
    <!-- messages tab -->
    <b-tabs pills card >
      <b-tab title="Key messages" >
       
           <b-input-group v-for="(keymes, index) in keymessages" :key="index" class="mb-3">
             <b-form-input type="text" :placeholder="`Key message ${index + 1}`" v-model="keymes.message" :name="`keymessages[${index}][message]`"></b-form-input>
             <b-input-group-append>
              <b-input-group-text  :id="`popover-1-${index}`" role="button" >
                <font-awesome-icon :icon="['fas', 'ellipsis-vertical']" class="ms-2 text-secondary" />
                <b-popover :target="`popover-1-${index}`" triggers="hover" placement="right">
                  <b-button size="sm" variant="secondary" class="mb-1 px-3">Edit</b-button><br>
                  <b-button @click="deleteKeyRow(index)" size="sm" variant="secondary">Delete</b-button>
             </b-popover>
              </b-input-group-text>
             </b-input-group-append> 
           </b-input-group>

           <div class="d-flex justify-content-between">
            <b-button variant="outline-secondary" :disabled='isKeyDisabled' @click="addKeyMessage"> + Add more</b-button>
            <b-button variant="primary" @click="onSubmit">Save</b-button>
           </div>
      </b-tab>
      <!-- questions tab -->
      <b-tab title="Interview questions">
        <div class="accordion" role="tablist">
    
      <b-card no-body class="mb-1">
       <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-1 variant="light" class="text-start">Key message 1</b-button>
      </b-card-header>
      <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-input-group v-for="(ques, index) in interviewQuestions" :key="index" class="mb-3">
             <b-form-input type="text" :placeholder="`Interview question ${index + 1}`" v-model="ques.message" :name="`interviewQuestions[${index}][question]`"></b-form-input>
             <b-input-group-append>
              <b-input-group-text  :id="`popover-1-${index}`" role="button" >
                <font-awesome-icon :icon="['fas', 'ellipsis-vertical']" class="ms-2 text-secondary" />
                <b-popover :target="`popover-1-${index}`" triggers="hover" placement="right">
                  <b-button size="sm" variant="secondary" class="mb-1 px-3">Edit</b-button><br>
                  <b-button @click="deleteQuesRow(index)" size="sm" variant="secondary">Delete</b-button>
             </b-popover>
              </b-input-group-text>
             </b-input-group-append> 
           </b-input-group>
           <div class="d-flex justify-content-between">
            <b-button variant="outline-secondary" :disabled='isQuesDisabled' @click="addInterviewQuestion"> + Add more</b-button>
            <b-button variant="primary" @click="onSubmit">Save</b-button>
           </div>
         
        </b-card-body>
      </b-collapse>
     </b-card>
     <b-card no-body class="mb-1">
       <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-2 variant="light" class="text-start">Key message 2</b-button>
      </b-card-header>
      <b-collapse id="accordion-2" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
         
        </b-card-body>
      </b-collapse>
     </b-card>
     <b-card no-body class="mb-1">
       <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-3 variant="light" class="text-start">Key message 3</b-button>
      </b-card-header>
      <b-collapse id="accordion-3" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
         
        </b-card-body>
      </b-collapse>
     </b-card>

  </div>
      </b-tab>
    </b-tabs>
  </b-card>
  </b-col>

  <b-col lg="6">
    <b-form-group label="Video title" label-for="video">
      <template slot="label">
          B-roll scene<span class="required">*</span>
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
          <b-form-tags v-model="value" no-outer-focus class="mb-2  bg-light ">
         <template v-slot="{ tags, inputAttrs, inputHandlers, tagVariant, addTag, removeTag }" >
        <b-input-group class="mb-2">
          <b-form-input
            v-bind="inputAttrs"
            v-on="inputHandlers"
            placeholder="Add b-roll"
            class="form-control"
          ></b-form-input>
          <b-input-group-append>
            <b-button @click="addTag()" variant="secondary">Add</b-button>
          </b-input-group-append>
        </b-input-group>
        <div class="d-inline-block" style="font-size: 1.2rem;">
          <b-form-tag
            v-for="tag in tags"
            @remove="removeTag(tag)"
            :key="tag"
            :title="tag"
            :variant="tagVariant"
            class="mr-1"
          >{{ tag }}</b-form-tag>
        </div>
      </template>
    </b-form-tags>
    </b-form-group>
  </b-col>

  <b-col lg="6" md="6" sm="6">
    <b-form-group id="producer" label="Producer" label-for="producer">
      <template slot="label">
          Location<span class="required">*</span>
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
          <b-form-select
        id="location"
        v-model="form.locations"
        :options="locations"
      ></b-form-select>
    </b-form-group>
  </b-col>

  <b-col lg="12">
    <b-form-group id="rg" label="Video description" label-for="description">
      <template slot="label">
         Notes<span class="required">*</span>
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
      <b-form-textarea
        id="description"
        v-model="form.description"
        placeholder="Text"
      ></b-form-textarea>
    </b-form-group>
  </b-col>

  

  
</b-row>


<div class="mt-3 d-flex justify-content-between">
  <b-button type="reset" variant="secondary" class=" text-white"><font-awesome-icon :icon="['fas', 'circle-xmark']" class="mr-2 "/>Cancel</b-button>
  <b-button type="submit" variant="success" class=" text-white"><font-awesome-icon :icon="['fas', 'circle-check']" class="mr-2 "/>Submit</b-button>
</div>
</b-form>

<!-- <b-card class="mt-3" header="Resultado">
<pre class="m-0">{{ form }}</pre>
</b-card> -->
        

    </div>


</template>

<script >
export default {
  data() {
    return {
      form: {
        videopurpose: "null",
        videostyle: null,
        broll: "",
        locations:null,
        notes: "null",
      
      },
      keymessages: [{
       
      }
    ],
    interviewQuestions: [{
       
      }
    ],
      
      videostyle: [
        { value: null, text: "Select" },
        { value: "Interview style", text: "Interview style" },
        { value: "Tour style", text: "Tour style" },
        { value: "Overview style", text: "Overview style" },
      ],
      locations: [
      { value: null, text: "Select" },
        { value: "Dance room", text: "Dance room" },
        { value: "Auditorium hall", text: "Auditorium hall" },
        { value: "Music hall", text: "Music hall" },
        { value: "Conference room", text: "Conference room" },
      ],
      
      show: true,
      selected: null,
      status: null,
    };
  },
  computed:{

    isKeyDisabled() {
     return this.keymessages.length == 5 ;
  },
  isQuesDisabled() {
     return  this.interviewQuestions.length == 3;
  }
  },

  methods: {
  
    addKeyMessage () {
      if(this.keymessages.length < 5) {
      this.keymessages.push({
        message: ''
      })}
    },
    deleteKeyRow(index) {
      this.keymessages.splice(index, 1);
    },

    addInterviewQuestion () {
      if(this.interviewQuestions.length < 3) {
      this.interviewQuestions.push({
        question: ''
      })}
    },
    deleteQuesRow(index) {
      this.interviewQuestions.splice(index, 1);
    },
    

    onSubmit(event) {
      const data = {
        keymessages: this.keymessages
      }
      // event.preventDefault();
      alert(JSON.stringify(data));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.videopurpose = "null";
      this.form.videostyle = null;
      this.form.keymessages = "";
      this.form.interviewquestions = "";
      this.form.broll = "";
      this.form.locations = null;
      this.form.notes = "";
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
    saveFile(event) {
      console.log(event);
    },
  },
};
</script>
<style >
.required {
  color: red;
}
.nav-pills .nav-link{
  background-color: rgb(248, 242, 242) !important;
  color: black;
  border: 1px solid grey;
}
.nav-pills .nav-link.active{
  background-color: black !important;
  color: white;
  font-weight:500;
}
</style>
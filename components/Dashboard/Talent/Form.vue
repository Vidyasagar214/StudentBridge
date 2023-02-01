<template>
    <div class="m-2">
     
  <b-form @submit="onSubmit" @reset="onReset" v-if="show" novalidate >
<b-card class="m-0 p-0" bg-variant="light" v-for="(index) in talentSelection" :key="index">
<b-row>

  <b-col lg="9">
    <b-form-group label="Talent" label-for="talent"  required>
      <template slot="label">
        Talent
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
      <b-form-select id="talent">
          <b-form-select-option disabled selected>Select talent</b-form-select-option> 
          <b-form-select-option>Alexis</b-form-select-option> 
          <b-form-select-option>Peter</b-form-select-option>
          <b-form-select-option>Convey</b-form-select-option> 
          <b-form-select-option>Bruce</b-form-select-option>       
      </b-form-select>
    </b-form-group>
  </b-col>

  <b-col lg="3" class="mt-4">
    <b-button variant="outline-secondary" class="mt-2" v-b-toggle.sidebar-right>
       <font-awesome-icon :icon="['fas', 'list-check']" class="me-1 text-secondary" />Assign topic
    </b-button>
  </b-col>

  <b-col lg="12">
    <b-card class="text-center">
      <b-card-group deck>
        <b-card >
      <b-card-text class="text-left">
       Key messages
      </b-card-text>
    </b-card>
    <b-card >
      <b-card-text class="text-left">
       Interview questions
      </b-card-text>
    </b-card>
      </b-card-group>
    </b-card>
  </b-col>
</b-row>

<b-row>
  <b-col lg="4" class="mt-4">
    <b-button variant="outline-secondary" > <font-awesome-icon :icon="['fas', 'location-dot']" class="me-2 text-secondary"/>Add location</b-button>
  </b-col>
</b-row>
  
<b-row class="mt-2">
  <b-col lg="6" md="6" sm="6">
    <b-form-group id="address"  label-for="address">
      <template slot="label">
          Mailing address
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
          <b-form-input
        id="address"
        placeholder="Text"
      ></b-form-input>
    </b-form-group>
  </b-col>
<b-col lg="6" md="6" sm="6">
    <b-form-group >
      <template slot="label">
          Location
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
          <b-form-select
        id="location"
        v-model="form.locations"
        :options="locations"
      ></b-form-select>
    </b-form-group>
  </b-col> 
</b-row>

<b-row>
  <b-col lg="6">

    <b-col lg="12" class="p-0">
    <b-form-group >
      <template slot="label">
          Location coordinator
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
          <b-form-select >
            <b-form-select-option disabled selected>Select</b-form-select-option>
            <b-form-select-option>Elizabeth Young</b-form-select-option>
            <b-form-select-option>James Brook</b-form-select-option>
            <b-form-select-option>Milley Jane</b-form-select-option>
            <b-form-select-option>Will Brian</b-form-select-option>
          </b-form-select>
    </b-form-group>
  </b-col>

  <b-col lg="12" class="p-0">
    <b-form-group >
    <template slot="label">
      B-roll scenes
            <font-awesome-icon :icon="['fas', 'circle-info']" class="ms-2 text-secondary"/>
          </template>
  <b-form-tags
      v-model="value"
      @input="resetInputValue()"
      tag-variant="success"
      class="mb-2 mt-2"
      :disabled="disabled"
      no-outer-focus
      placeholder="Enter b-roll"
      :state="state"
    >
      <template v-slot="{tags, inputId, placeholder, disabled, addTag, removeTag }">
        <b-input-group>
          <b-form-input
            v-model="newTag"
            :id="inputId"
            :placeholder="placeholder"
            :disabled="disabled"
          ></b-form-input>
          <b-input-group-append>
            <b-button @click="addTag(newTag)"  variant="secondary">Add</b-button>
          </b-input-group-append>
        </b-input-group>
        <ul v-if="tags.length > 0" class="mb-0">
          <li v-for="tag in tags" :key="tag" :title="`Tag: ${tag}`" class="mt-2">
            <span  class="d-flex align-items-center">
              <span class="mr-2">{{ tag }}</span>
              <font-awesome-icon :icon="['fas', 'circle-xmark']" 
                class="ms-2 text-danger "
                role="button"  
                :disabled="disabled"
                @click="removeTag(tag)"/>
            </span>
          </li>
        </ul>
      </template>
    </b-form-tags>
  </b-form-group>
  </b-col>
  </b-col>
 <b-col lg="6">
  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1398161.7766810898!2d-88.59483423127702!3d42.81407519365977!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88055dcec980d25b%3A0xd756ee5f0e66a5b3!2sCarthage%20College!5e0!3m2!1sen!2sin!4v1674056701930!5m2!1sen!2sin" width="300" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe></b-col>
</b-row>
</b-card>

<div class="d-flex justify-content-between my-2">
  <b-button type="reset" variant="outline-secondary"  @click="addTalentCard">
    <font-awesome-icon :icon="['fas', 'user-plus']" class="mr-2 "/>Add more talent
  </b-button>
  <b-button type="reset" variant="outline-secondary" v-show="isKeyDisabled"  @click="deleteTalentCard(index)">
    <font-awesome-icon :icon="['fas', 'user-minus']"  class="mr-2 "/>Remove talent
  </b-button>
</div>


<div class="mt-5 d-flex justify-content-between">
  <b-button type="reset" variant="secondary" class=" text-white">
    <font-awesome-icon :icon="['fas', 'circle-xmark']" class="mr-2 "/>Cancel
  </b-button>
  <b-button type="submit" variant="success" class=" text-white">
    <font-awesome-icon :icon="['fas', 'circle-check']" class="mr-2 "/>Submit
  </b-button>
</div>
</b-form>
  
<AssignTopicPopover />

</div>
</template>

<script >
import AssignTopicPopover from './AssignTopicPopover.vue';
export default {
  components: { AssignTopicPopover },
  data() {
    return {
      form: {
        newTag: '',
        isHidden:true,
        value: []
      
      }, 
      locations: [
      { value: null, text: "Select" },
        { value: "Dance room", text: "Dance room" },
        { value: "Auditorium hall", text: "Auditorium hall" },
        { value: "Music hall", text: "Music hall" },
        { value: "Conference room", text: "Conference room" },
      ],
      talentSelection:[
        {
        }
      ]
      ,
      show: true,
      selected: null,
      status: null,
    };
  },
  computed:{

isKeyDisabled() {
 return this.talentSelection.length !== 1 ;
},

},

  methods: {
  
    resetInputValue() {
        this.newTag = ''
      },
      addTalentCard () {
      this.talentSelection.push({
      })
    },
    deleteTalentCard(index) {
      this.talentSelection.splice(index, 1);
    },

    onSubmit(event) {
      event.preventDefault();
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
}

</script>
<style >
</style>
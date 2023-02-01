<template>
<div>

    <vue-cal
      ref="vuecal"
      :disable-views="['years', 'year','month']"  
       active-view="week"
      :time-from="8 * 60"
      :time-to="20 * 60"
      :time-step="60"
      :events= "events"
      :drag-to-create-event="false"
      cell-contextmenu
    
     >
    </vue-cal>
  </div>
  </template>
  
  <script >
  import VueCal from 'vue-cal'
  import 'vue-cal/dist/vuecal.css'

  export default {
    components: { VueCal},
    data: () => ({
    events: [
  {
    start: '2023-01-25 10:00',
    end: '2023-01-25 11:00',
    // You can al2023-01-25so define event dates with Javascript Date objects:
    // start: new Date(2018, 11 - 1, 16, 10, 30),
    // end: new Date(2018, 11 - 1, 16, 11, 30),
    title: 'Alexis',
    content: 'Music room'
  },{
    start: '2023-01-26 12:00',
    end: '2023-01-26 13:00',
    // You can also define event dates with Javascript Date objects:
    // start: new Date(2018, 11 - 1, 16, 10, 30),
    // end: new Date(2018, 11 - 1, 16, 11, 30),
    title: 'David',
    content: 'Auditorium',
  },
  {
    start: '2023-01-27 15:00',
    end: '2023-01-27 16:00',
    // You can also define event dates with Javascript Date objects:
    // start: new Date(2018, 11 - 1, 16, 10, 30),
    // end: new Date(2018, 11 - 1, 16, 11, 30),
    title: 'Peter',
    content: 'Music room'
  }

]
})
  }
 </script>
  
  <style>
  .vuecal {height: 90vh;}

  .vuecal__event{
    color: rgb(22, 3, 3);
    background-color: rgb(150, 150, 23);
  }
 </style>
  
<script>
import '@fullcalendar/core/vdom' // solves problem with Vite
import FullCalendar from '@fullcalendar/vue3'
import dayGridPlugin from '@fullcalendar/daygrid'
import timeGridPlugin from '@fullcalendar/timegrid'
import interactionPlugin from '@fullcalendar/interaction'

export default {
  components: {
    FullCalendar // make the <FullCalendar> tag available
  },
  data() {
    return {
      calendarOptions: {
        plugins: [ dayGridPlugin, timeGridPlugin, interactionPlugin ],
        initialView: 'dayGridMonth',
        // Don't show the weekends
        weekends: false,
        // Define the header for the calendar
        headerToolbar: {
          left: 'prev,next today',
          center: 'title',
          right: 'dayGridMonth,timeGridWeek,timeGridDay'
        },
        // Define Event Data
        events: 'https://gist.githubusercontent.com/steinbring/80157cc5866de53c8cd975a1673f4425/raw/72d8dfb2880b76ffbd7bb8a48f3803aab3b804ba/events.json'
      }
    }
  }
}
</script>
<template>
  <FullCalendar :options="calendarOptions" />
</template>
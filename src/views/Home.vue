<template>
  <div class="home px-4 py-2">

    <div class="col-12 d-flex  px-2">


      <div class="col-4 px-4 py-4 mt-5">


   

          <form  class="card px-3 py-4">
  <div class="mb-3">
    <h4>Schedule Event</h4>
    <label for="exampleInputEmail1" class="form-label">Event Title</label>
    <input type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <!-- <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div> -->
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Event Date</label>
    <input type="date" class="form-control" id="exampleInputPassword1">
  </div>
  <!-- <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div> -->
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
        <form  class="card px-3 py-4 mt-4">
  <div class="mb-3">
    <h4>Plan Day</h4>
    <label for="exampleInputEmail1" class="form-label">Select Day</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
   
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Input Activities</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <!-- <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div> -->
  <button type="submit" class="btn btn-primary">Submit</button>
</form>

 
      </div>

      <div class="col-8 py-4">
         <h2 class="text-center">Interactive Calendar</h2>
          <calendar-view 
        style="height: 75vh"
        :show-date="showDate"
        class="theme-default holiday-us-traditional holiday-us-official col-12 mt-2 py-3"
      >
        <template #header="{ headerProps }">
          <calendar-view-header
            :header-props="headerProps"
            @input="setShowDate"
              @click-date="logDate"
          />
        </template>
      </calendar-view>
      </div>
    
    </div>
  </div>
</template>

<script>
import { CalendarView, CalendarViewHeader } from "vue-simple-calendar";
import "vue-simple-calendar/dist/style.css";
// The next two lines are optional themes
import "vue-simple-calendar/static/css/default.css";
import "vue-simple-calendar/static/css/holidays-us.css";

export default {
  name: "Home",
  data: function () {
    return { showDate: new Date(),
    selectedDate:'' };
  },
  components: {
    CalendarView,
    CalendarViewHeader,
  },
  methods: {
    setShowDate(d) {
      this.showDate = d;
    },
    logDate(date){
// this.selectedDate= moment(date).format('YYYY-MM-DD')
console.log(date)}
  },
};
</script>

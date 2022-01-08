<template>
  <div class="home px-4 py-2">
    <h1 class="text-center">My Calendar</h1>

    <div class="col-12 d-flex mt-5 px-2">
      <div class="col-4">forms</div>
      <calendar-view
        style="height: 75vh"
        :show-date="showDate"
        class="theme-default holiday-us-traditional holiday-us-official col-8"
      >
        <template #header="{ headerProps }">
          <calendar-view-header
            :header-props="headerProps"
            @input="setShowDate"
          />
        </template>
      </calendar-view>
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
    return { showDate: new Date() };
  },
  components: {
    CalendarView,
    CalendarViewHeader,
  },
  methods: {
    setShowDate(d) {
      this.showDate = d;
    },
  },
};
</script>

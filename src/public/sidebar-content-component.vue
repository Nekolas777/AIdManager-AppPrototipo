<script>
import HomeIcon from '../assets/home-icon.svg';
import ProjectIcon from '../assets/project-icon.svg';
import AnalyticsIcon from '../assets/analytics-icon.svg';
import CalendarIcon from '../assets/calendar-icon.svg';
import TeamIcon from '../assets/team-icon.svg';

export default {
  name: "sidebar-content",
  components: {
    HomeIcon,
    ProjectIcon,
    AnalyticsIcon,
    CalendarIcon,
    TeamIcon
  },
  props: {
    sidebarVisible: {
      type: Boolean,
      required: true
    }
  },
  // for testing
  /*updated() {
    console.log(this.sidebarVisible);
  }*/
}
</script>

<template>
  <transition name="slide">
    <aside v-show="sidebarVisible">
      <div class="py-5 pl-3 h-full flex flex-column justify-content-between">
        <ul class="flex flex-column gap-3">
          <li class="flex flex-row gap-3 align-items-center py-3 pl-4 border-round-md">
            <HomeIcon></HomeIcon>
            <p class="font-medium text-base">Home</p>
          </li>
          <li class="flex flex-row gap-3 align-items-center py-3 pl-4 border-round-md">
            <ProjectIcon></ProjectIcon>
            <p class="font-medium text-base">Projects</p>
          </li>
          <li class="flex flex-row gap-3 align-items-center py-3 pl-4 border-round-md">
            <AnalyticsIcon></AnalyticsIcon>
            <p class="font-medium text-base">Analytics</p>
          </li>
          <li class="flex flex-row gap-3 align-items-center py-3 pl-4 border-round-md">
            <CalendarIcon></CalendarIcon>
            <p class="font-medium text-base">Calendar</p>
          </li>
          <li class="flex flex-row gap-3 align-items-center py-3 pl-4 border-round-md">
            <TeamIcon></TeamIcon>
            <p class="font-medium text-base">Team</p>
          </li>
        </ul>
        <div class="pr-5">
          <div class="flex flex-row border-top-1 border-gray-500 gap-3 align-items-center pt-4 pl-4">
            <div class="inline-flex gap-3 cursor-pointer">
              <i class="pi pi-sign-out text-gray-700" style="font-size: 1.5rem;"></i>
              <p class="font-medium text-gray-700">Log out</p>
            </div>
          </div>
        </div>
      </div>
    </aside>
  </transition>
</template>

<style scoped>

aside {
  border-right: 2px solid #BABABA;
}

.inline-flex:hover i,
.inline-flex:hover p {
  color: red !important;
  transition: all 0.3s;
  transition-timing-function: ease;
}

li > p{
  letter-spacing: .5px;
  color: #02513D;
}

li {
  cursor: pointer;
}

li:first-child {
  background-color: #E6EEEC;
}

li:hover {
  transition: all 0.2s ease;
  background-color: #e0e0e0;
}

aside {
  position: fixed;
  margin-top: 113px;
  bottom: 0;
  top: 0;
  width: 300px;
  z-index: 99;
  background-color: #f8f8f8;
}

/*esta clases son de la etiqueta "transition"*/

.slide-enter {
  transform: translateX(-120%);
}

.slide-enter-active {
  transform: translateX(0);
  transition: transform 0.4s ease-out;
}

.slide-leave {
  transform: translateX(0);
}

.slide-leave-active {
  transform: translateX(-120%);
  transition: transform 0.4s ease-out;
}


@media (min-width: 1024px) {
  aside {
    position: relative;
    margin-top: 0;
    height: 100%;
    width: 350px;
  }
}


</style>
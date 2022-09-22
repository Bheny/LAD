<template>
  <div id="app" class="flex">
      <SideMenu />
      <DashboardSection />
      <ProfileSection />
      
  </div>
  
</template>

<script>
import SideMenu from "./components/SideMenu";
import DashboardSection from "./components/Dashboard";
import ProfileSection from "./components/Profile";


export default {
  name: 'App',
  components: { SideMenu, DashboardSection, ProfileSection, },

        
    }
 
</script>

<style>

</style>

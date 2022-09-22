<template>
    <div id="DashboardSection" class="p-6 w-4/5">
        <div class="w-full  ">
            <div class=" p-2 w-full">
               <div class=" w-1/3 border inline-block"> 
                    <h2 class="text-gray-900 font-bold text-xl">Welcome Back, {{ user.firstname }}!</h2>
                    <h3 class="text-gray-600 text-sm">April 30, Thursday</h3>
                </div>
                <div class="w-1/3 border border inline-block pt-2  flex gap-3">
                    <input type="search" class="rounded-lg bg-white border p-3" /><button class="p-3 border">search</button>
                </div>
                <!-- message and notification icons container -->
                <div class="w-12 inline-block pt-2 float-right flex gap-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                    </svg>
                </div>
            </div>
            
        </div>

       <div class="flex gap-3">
             <div class="border border-gray-300 rounded-lg p-3 w-2/5 inline-block   ">
            <div class="w-full">
                <h2 class="font-bold text-lg p-2 inline-block">Intro:Curse Engineering </h2>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-gray-600 float-right inline-block" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M4 8V4m0 0h4M4 4l5 5m11-1V4m0 0h-4m4 0l-5 5M4 16v4m0 0h4m-4 0l5-5m11 5l-5-5m5 5v-4m0 4h-4" />
</svg>
            </div>
            <div class="pb-3 ">
                <iframe width="150" height="200" class="w-full rounded-lg" src="https://www.youtube.com/watch?v=Zc14ZkWVhhs&t=15s">
                </iframe>
            </div>
            <div class="pb-6 w-full">
                <div class="flex pb-2 relative inline-block w-1/2">
                    <img src="../assets/profile.jpg" class="border border-gray-400 border-2 absolute w-8 h-8 rounded-full" />
                    <img src="../assets/profile.jpg" class="border border-gray-400 border-2 absolute ml-6 w-8 h-8 rounded-full" />
                    <img src="../assets/profile.jpg" class="border border-gray-400 border-2 absolute ml-12 w-8 h-8 rounded-full" />
                    <div class="w-8 h-8 rounded-full bg-gray-300 absolute ml-16 text-gray-500 text-xs pt-2 pl-1 font-bold">+12</div>
                </div>
                <div class="float-right -mt-2">
                    <button class="rounded-full pl-2 pr-2 bg-blue-600 text-gray-100 -mt-4 text-sm p-2">Enter the Class</button>
                </div>
            </div>
            <div class="mt-4 w-full border-gray-400 border-t p-2">
                <span class="font-bold inline-block mr-2">35%</span>
                <div class="w-2/3 rounded-full bg-gray-400 inline-block">
                    <div class="rounded-full bg-blue-700 w-1/2 p-1"></div>
                </div>
                <span class="pl-2 font-bold">3<sub class="text-gray-400 font-bold">/9</sub></span>
            </div>
        </div>
         <div class="border border-gray-300 rounded-lg p-3 inline-block  w-1/2">
            <div class="w-full">
                <h2 class="font-bold text-lg p-2 inline-block">Activity</h2>
                <select v-model="data" class="bg-gray-300 rounded-lg float-right p-2">
                    <option value="Monthly" selected>Monthly</option>
                    <option value="Weekly" >Weekly</option>
                    <option value="Daily" >Daily</option>
                </select>
            </div>
            <div>
                <BarChart :chartData="chartData" />
                
            </div>
           
        </div>
       </div>
       <div class="w-full">
        <div class="border border-gray-400 rounded-lg mt-4">
            <div class="p-2 w-full">
                <h2 class="font-bold text-lg p-2 inline-block">Timeline</h2>
                <div class="flex gap-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
</svg>
<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
</svg>
                </div>
            </div>
        </div>
       </div>
        </div>
</template>

<script>
import BarChart from './BarChart'

export default {
    name:'DashboardSection',
    components: {BarChart},
    data(){
        return {
            user: {
        id:1,
        username:"0321080183",
        firstname:"Bernard Kojo",
        lastname: "Tay",
        is_student:true,
        class:"Btech Computer Science 300",
      },
            courses: {
                title:"Intro to Database 1",
                
            },
            chartDataDaily: {
        labels: [ 'Monday', 'Tuesday'],
        datasets: [ { data: [40, 20] } ]
      },
        }
    },
    methods: {
        getChartsfor: function(x){
            if ( x === 'Daily'){
                return this.chartDataDaily;
            }
        }
    }
}
</script>
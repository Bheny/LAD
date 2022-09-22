<template>
    <div id="sideMenu" class="inline p-4 border-r h-full pt-4  w-2/6">
      <h2 class="text-blue-600 font-bold text-xl text-center shadow-lg p-3 mb-8">HTU LEARNING ANALYTICS</h2>
        <ul class="p-2">
            <li  class="p-2 mb-4 flex gap-4 " :class="[active ? 'font-bold text-blue-600':'text-gray-600', '']" ><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
</svg>Overview</li>
<li class="p-2 mb-4  text-gray-600 hover:font-bold  hover:text-blue-600" ><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 inline  mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
</svg>Team <div class="bg-red-600 pl-2 pr-2 pt-1 pb-1  text-gray-100 text-xs float-right rounded-lg">2</div></li>
            <li class="p-2 mb-4 flex gap-4 text-gray-600 hover:font-bold hover:text-blue-600" ><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
</svg>Analytics

</li>
            <li class="p-2 mb-4 flex gap-4 text-gray-600 hover:font-bold hover:text-blue-600" ><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
</svg>Settings</li>
            <li class="p-2 mb-4 flex gap-4 text-gray-600 hover:font-bold hover:text-blue-600" ><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1" />
</svg> Logout</li>
        </ul>
        <ul>
            <li class="p-2 text-lg text-gray-600">Classes</li>
            <li class="pl-4"><ul>
                <li v-for="course in mycourses" v-bind:key="course.id" class="p-2 w-full text-gray-500 text-sm"><div :class="course.color" class="inline-block mr-3 rounded-full mt-3 w-2 h-2"></div><div class="inline text-gray-800 font-bold">{{ course.title }}</div><div class="bg-gray-400 pl-2 pr-2 pt-1 pb-1  text-gray-600 text-xs float-right rounded-lg">{{ course.notifications}}</div></li>
                <li @click="load_more()"  class="flex p-3 pl-0 gap-3 text-gray-500 font-bold"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
</svg>Show {{show}}</li>
            </ul></li>
        </ul>
    </div>
</template>

<script>
export default { 
    name: 'sideMenu',
    data(){
     return {
        
      menus: [{id:1,name:"Dashboard",svg:"X"},
             {id:2,name:"Analytics",svg:""},
            ],
    mycourses: [{id:1,title:"Database 1", color:"bg-blue-600",notifications:7},
                {id:2,title:"MIS", color:"bg-red-600",notifications:11},
                {id:3,title:"Computer Literacy", color:"bg-green-600",notifications:4}],
    active:true,
    show:"More",

    }
    
  },
   computed: {
    fullname(){
      return `${this.user.firstname} ${this.user.lastname}`
    }
  },
  methods: {
    load_more() {
      this.show = "Less";
     let  more_courses = [{id:4,title:"Linux", color:"bg-yellow-600",notifications:3},{id:5,title:"Programming with Java", color:"bg-purple-600",notifications:20} ]
                more_courses.forEach(element => {
                  this.mycourses.push(element)
                });
      
    }
  }
}

</script>
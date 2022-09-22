<template> 
    <div id="CalenderModule" class="w-full rounded-lg bg-white mt-2">
        
        <div class="rounded-lg p-2 w-full">
            <div class="w-full">
                <div @click="decreaseMonth" class="w-6 float-left inline-block"><!-- left chevron -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
</svg>
                </div>
                <div class="w-48 inline-block text-center font-bold"><!-- date section -->
                    {{ months[count] }}, 2021
                </div>
                <div @click="increaseMonth" class="w-6 float-right inline-block"><!-- Right chevron -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
</svg>
                </div>
            </div>
            <div class="mt-2">
                <!--table class="text-center text-gray-500 w-full">
                    <thead >
                        <th>S</th>
                        <th>M</th>
                        <th>T</th>
                        <th>W</th>
                        <th>T</th>
                        <th>F</th>
                        <th>S</th>
                    </thead>
                    <tbody>
                        <tr v-for="x in 5" :key="x">
                            <td v-for="i in 7" :key="i">{{x}}</td>
                        </tr>
                    </tbody>
                </table-->
                <div class="grid text-gray-500 grid-cols-7 gap-3">
                    <th>S</th>
                        <th>M</th>
                        <th>T</th>
                        <th>W</th>
                        <th>T</th>
                        <th>F</th>
                        <th>S</th>
                
                    <button class="text-center text-gray-800" v-for="x in 30" :key="x">{{x}}</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script> 
export default {
    name:'CalenderModule',
    data(){
        return {
            count:0,
            months:['January','Febuary','March','April','May','June','July','August','September','October','November','December']
        }
    
    },
    methods: {
        increaseMonth(){
            this.count++;
        },
        decreaseMonth(){
            this.count--;
        },
    }
}
</script>
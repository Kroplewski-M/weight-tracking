<template>
  <section>
        <div class="flex text-zinc-300 mt-[100px]">
          <p class="font-bold ">Weight history-</p>
          <p class="ml-[180px]">View:</p>
          <a href="#" class="ml-[20px] font-bold underline">Tabs</a>
          <a href="#" class="ml-[30px]">Graph</a>
        </div>
        <div v-for="record in weightRecords" :key="record">
          <div class="w-[500px] h-[100px] bg-[#222222] rounded-md mt-10 mx-auto text-zinc-300 text-center hover:scale-[1.1] hover:cursor-pointer transition-transform	">
              <p class="font-semibold text-[30px] pt-[25px]">2019-11-13 - {{record}}kg</p>
          </div>
        </div>
      </section>
</template>

<script>
export default {
    name:"AppWeightTracker",
    props: ["weightRecords"],
    data(){
        return{
            dates:[],
            weights:[],
        }
    },
    methods:{
      
    }
}
</script>


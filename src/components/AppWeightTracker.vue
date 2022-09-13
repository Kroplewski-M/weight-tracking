<template>
  <section>
        <div class="flex text-zinc-300 mt-[100px]">
          <p class="font-bold ">Weight history-</p>
        </div>
        <section >
            <div v-for="date in dates" :key="date">
            <div class="w-[500px] h-[100px] bg-[#222222] rounded-md mt-5 mx-auto text-zinc-300 text-center hover:scale-[1.1] hover:cursor-pointer transition-transform">
                <p class="font-semibold text-[30px] pt-[25px]">{{date}} - {{this.weightRecords[date]}}kg</p>
            </div>
            </div>
        </section>
      </section>
</template>

<script>
export default {
    name:"AppWeightTracker",
    props: ["weightRecords"],
    data(){
        return{
            dates:[],
        }
    },
    methods:{
        getAllWeights(){
            const weights = Object.keys(this.weightRecords);
            weights.sort((a,b) =>  new Date(b) - new Date(a));

            for(let i=0; i < weights.length; i++){
                this.dates.push(weights[i]);
            }
        },
        
    },
    created(){
        this.getAllWeights();
    }
}
</script>


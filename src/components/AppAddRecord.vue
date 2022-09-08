<template>
    <section class="absolute h-[100vh] w-[100%] backdrop-blur-md">
        <div class="w-[400px] h-[350px] rounded-md bg-[#333333] left-[41.5%] mt-16 mx-auto text-zinc-200">
            <img src="@/assets/close.png" alt="" @click.prevent="closeAddRecord" class="float-right w-[30px] mr-[5px] mt-[5px] hover:cursor-pointer">
            <p class="font-bold text-[25px] text-center w-[80%] mx-auto pt-5">Add Record</p>
            <div class="w-[350px] mx-auto">
                <input required type="number" v-model="weight" placeholder="Weight (kg)" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <input required type="date" v-model="date" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <button class="mt-[50px] ml-[115px] w-[100px] h-[30px] rounded-md bg-purple-500 hover:bg-purple-600" @click.prevent="addWeightRecord">Submit</button>
            </div>
        </div>
  </section>
</template>

<script>
export default {
    name:"AddRecord",
    data(){
        return{
            weight: "",
            date: "",
        }
    },
    methods:{
        closeAddRecord(){
            this.$emit("closeAddRecord");   
        },
        addWeightRecord(){
            this.$emit("addWeightRecord",this.weight,this.date);
            this.weight = "";
            this.date = "";
        },
    }
}
</script>

<template>
    <section class="absolute h-[100vh] w-[100%] backdrop-blur-md">
        <div class="w-[400px] h-[350px] rounded-md bg-[#333333] left-[41.5%] mt-16 mx-auto text-zinc-200">
            <img src="@/assets/close.png" alt="" @click.prevent="closeAddRecord" class="float-right w-[30px] mr-[5px] mt-[5px] hover:cursor-pointer">
            <p class="font-bold text-[25px] text-center w-[80%] mx-auto pt-5">Add Record</p>
            <div class="w-[350px] mx-auto">
                <input required type="number" v-model="weight" placeholder="Weight (kg)" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <input required type="date" v-model="date" :max="max" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <p class="absolute right-[45%] mt-5 text-red-600" :class="showError">Please input valid information</p>
                <button class="mt-[80px] ml-[115px] w-[100px] h-[30px] rounded-md bg-purple-500 hover:bg-purple-600" @click.prevent="addWeightRecord">Submit</button>
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
            showError:"hidden",
            max: new Date().toISOString().split("T")[0],
        }
    },
    methods:{
        closeAddRecord(){
            this.$emit("closeAddRecord");   
        },
        addWeightRecord(){
            if(this.weight == "" || this.date == ""){
                this.showError = "";
                return;
            }
            this.showError = "hidden";
            this.$emit("addWeightRecord",this.weight,this.date);
        },
    },

}
</script>

<template>
  <section class="absolute h-[100vh] w-[100%] backdrop-blur-md">
        <div class="w-[400px] h-[550px] rounded-md bg-[#333333] left-[41.5%] mt-16 mx-auto text-zinc-200">
            <p class="font-bold text-[25px] text-center w-[80%] mx-auto pt-5">Welcome to your weight tracking app!</p>
            <p class="mt-[35px] ml-5">Please give us some details to start...</p>
            <div class="w-[350px] mx-auto">
                <input required type="text" placeholder="Name" name="name" v-model="name" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <input required type="number" placeholder="Weight (kg)" v-model="weight" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <input required type="date" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800" v-model="date" :max="max">
                <p class="absolute right-[46.5%] mt-5 text-red-600" :class="showError">Please fill in all information</p>
                <button class="mt-[80px] ml-[115px] w-[100px] h-[30px] rounded-md bg-purple-500 hover:bg-purple-600" @click.prevent="submit">Submit</button>
            </div>
        </div>
  </section>
</template>

<script>
export default {
    name:"AppWelcome",
    data(){
        return{
            name: "",
            weight: "",
            date: "",
            showError:"hidden",
            max: new Date().toISOString().split("T")[0],
        };
    },
    methods:{
        submit(){
            if(this.weight == "" || this.date == "" || this.name == ""){
                this.showError = "";
                return;
            }
            this.showError = "hidden";
            this.$emit('submit', this.name,this.weight,this.date);
        }
    }
}
</script>


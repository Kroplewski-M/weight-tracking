<template>
  <div class="w-[100vw] h-[25px] bg-red-700 absolute left-0 pb-5">
    <p class="text-center text-zinc-300 font-bold">All Information is stored on the local storage so please do not delete it as you will lose all information</p>
  </div>
    <section class="pt-5">
          <p class="text-zinc-300 text-center pt-5 pb-[10px] text-[20px]">Welcome, {{name}}</p>
          <div class="w-[400px] h-[200px] rounded-tl-[510px] rounded-tr-[510px] bg-transparent border-solid border-[15px] border-purple-500 border-b-0 mt-[10px] mx-auto text-center">
            <p class="font-bold text-zinc-300 mt-10">Current Weight-</p>
            <p class="font-bold text-[70px] text-zinc-300 mt-[30px]">{{currentWeight}}kg</p>
          </div>
          <div class="mx-auto w-[100px] mt-10">
            <button class="w-[100px] h-[30px] bg-purple-500 hover:bg-purple-600 text-zinc-100 font-bold rounded-md" @click.prevent="addRecord">Add Record</button>
          </div>
      </section>
</template>

<script>
export default {
    name: "AppOverview",
    props:["name","currentWeight"],
    methods:{
      addRecord(){
        this.$emit('addRecord');
      }
    }
}
</script>

<style>

</style>
<template>
    <section class="absolute h-[100vh] w-[100%] backdrop-blur-md">
        <div class="w-[400px] h-[350px] rounded-md bg-[#333333] left-[41.5%] mt-16 mx-auto text-zinc-200">
            <p class="font-bold text-[25px] text-center w-[80%] mx-auto pt-5">Add Record</p>
            <div class="w-[350px] mx-auto">
                <input type="number" placeholder="Weight (kg)" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <input type="date" class="ml-5 mt-10 mx-auto w-[300px] h-[30px] rounded-md pl-[10px] bg-zinc-800">
                <button class="mt-[50px] ml-[115px] w-[100px] h-[30px] rounded-md bg-purple-500 hover:bg-purple-600">Submit</button>
            </div>
        </div>
  </section>
</template>

<script>
export default {

}
</script>

<template>
  <div class="w-[99vw] h-[100vh] bg-[#111111]">
      <AppWelcome :class="showWelcome" @submit="submit"></AppWelcome>
      <AppAddRecord :class="showAddRecord" @closeAddRecord="closeAddRecord" @addWeightRecord="addWeightRecord"></AppAddRecord>
      <div class="w-[800px] mx-auto">
        <AppOverview :name="name" :currentWeight="currentWeight" @addRecord="addRecord"></AppOverview>
        <AppWeightTracker></AppWeightTracker>
    </div>
  </div>
</template>

<script>
  import AppWeightTracker from '@/components/AppWeightTracker.vue'
  import AppWelcome from '@/components/AppWelcome.vue'
  import AppOverview from '@/components/AppOverview.vue'
  import AppAddRecord from './components/AppAddRecord.vue'

  export default{
    name:"App",
    components: {
    AppWelcome,
    AppWeightTracker,
    AppOverview,
    AppAddRecord,
},
  data(){
    return{
      name: "",
      weightRecords: {},
      showWelcome: 'hidden',
      showAddRecord: 'hidden',
      currentWeight: 0,
    };
  },
  methods:{
    submit(name,weight,date){
      this.showWelcome = 'hidden';

      this.name = name;
      localStorage.setItem('name',name);


      this.weightRecords[date] = weight;
      this.currentWeight = Object.values(this.weightRecords)[0];
      localStorage.setItem('weightRecords', JSON.stringify(this.weightRecords));
    },
    addRecord(){
      this.showAddRecord = "";
    },
    closeAddRecord(){
      this.showAddRecord = "hidden";
    },
    addWeightRecord(weight,date){
      this.weightRecords[date] = weight;
      console.log(this.weightRecords);
      localStorage.setItem('weightRecords', JSON.stringify(this.weightRecords));
      this.showAddRecord = "hidden";
    }
  },  
  created(){
    let name = localStorage.getItem('name');
    if(name == undefined){
      this.showWelcome = '';
    }
    else{
      this.showWelcome = 'hidden';
      this.name = name;
    }

    let records = localStorage.getItem('weightRecords');
    if(records == null){
      console.log("weightRecords null");
    }else{
      this.weightRecords = JSON.parse(records);
      this.currentWeight = Object.values(this.weightRecords)[0];
      console.log(this.weightRecords);
    }
  },
  watch:{
   
  }
  }

</script>

